---
tags:
  - dsa
  - system-design
  - trade-offs
  - architecture
stage: 6
type: architecture
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - System Trade-offs
  - Trade-offs & System Architecture Decisions
  - Đánh đổi trong thiết kế hệ thống
---

# 🏛️ Ma Trận Đánh Đổi & Quyết Định Thiết Kế Hệ Thống (Trade-offs in System Architecture)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Triết Lý Cốt Lõi
Trong kỹ thuật phần mềm và thiết kế hệ thống quy mô lớn:
> *"Không có giải pháp hoàn hảo. Mọi quyết định kỹ thuật đều là một **Sự Đánh Đổi (Trade-off)** có chủ đích."*

Nhiệm vụ của người kỹ sư/kiến trúc sư không phải là tìm ra cấu trúc "xịn nhất", mà là chọn cấu trúc có **ưu điểm giải quyết đúng nút thắt cổ chai** và **nhược điểm nằm trong ngưỡng chấp nhận được** của hệ thống.

---

## 2. Bảng Ma Trận Đánh Đổi Cốt Lõi (Core Trade-off Matrix)

| Chiều Đánh Đổi | Lựa Chọn A (Tối ưu tiêu chí này) | Lựa Chọn B (Tối ưu tiêu chí kia) | Bối Cảnh Thực Tế |
| :--- | :--- | :--- | :--- |
| **Thời Gian vs Không Gian (Time vs Space)** | Dùng [[Hash Table & HashSet\|Hash Table]] ($O(1)$ Time) $\to$ Tốn thêm $O(n)$ RAM | Dùng In-place [[Two Pointers Pattern\|Two Pointers]] ($O(1)$ Space) $\to$ Mất công sort $O(n \log n)$ | Hệ thống nhúng (Embedded) chọn B; Máy chủ Backend chọn A. |
| **Đọc Nhanh vs Ghi Nhanh (Read-heavy vs Write-heavy)** | Dùng [[Array & Dynamic Array\|Array]] / B-Tree Index $\to$ Đọc cực nhanh $O(1)/O(\log n)$, nhưng ghi/chèn chậm do phải re-index | Dùng [[Linked List]] / LSM-Tree $\to$ Ghi chớp nhoáng $O(1)$ Append-only, nhưng đọc phải quét qua memtable | CSDL SQL (Read-heavy) chọn A; CSDL Time-series / Log (Write-heavy) chọn B. |
| **Độ Chính Xác vs Tiết Kiệm RAM (Exact vs Probabilistic)** | Dùng `HashSet` lưu toàn bộ String $\to$ Chính xác $100\%$, ngốn hàng chục GB RAM | Dùng [[Bloom Filter]] $\to$ Chỉ tốn vài chục MB RAM, chấp nhận rủi ro $1\%$ Dương tính giả | Kiểm tra URL độc hại, ngăn chặn Cache Penetration chọn B. |
| **Sắp Xếp In-place vs Ổn Định Tuyệt Đối (Stability vs Space)** | Dùng [[Quick Sort]] $\to$ In-place $O(\log n)$ Space, nhưng Unstable và có thể dính Worst-case | Dùng [[Merge Sort]] $\to$ Luôn luôn $O(n \log n)$ và Stable, nhưng tốn $O(n)$ RAM phụ | Sắp xếp dữ liệu trong RAM chọn A; Sắp xếp dữ liệu Linked List hoặc trên đĩa chọn B. |

---

## 3. Kiến Trúc Sư Áp Dụng DSA Vào Đời Thực Như Thế Nào?

```
[Web Client] 
     │
     ▼
[Nginx / API Gateway] ──► Trie Prefix Tree (Khớp Router URL trong O(L))
     │
     ▼
[App Layer / Memory] ──► LRU Cache (Hash Table + Doubly Linked List O(1))
     │
     ▼
[Storage Engine]    ──► Bloom Filter (Tránh đọc đĩa vô ích)
     │
     ▼
[Disk Database]     ──► B+ Tree / LSM Tree (Tối ưu Disk I/O Blocks)
```

1. **Khớp URL Request:** Sử dụng [[Trie (Prefix Tree)|Trie]] để tìm handler tương ứng trong thời gian bằng độ dài URL $O(L)$, độc lập với hàng nghìn API routes.
2. **Bộ nhớ đệm tầng ứng dụng:** Sử dụng [[LRU Cache]] để phục vụ $90\%$ request đọc thường xuyên trong $O(1)$.
3. **Trước khi chạm vào ổ cứng:** Sử dụng [[Bloom Filter]] để kiểm tra nhanh xem key có trong database không; nếu không có thì hủy request ngay lập tức mà không tốn I/O đĩa.
4. **Tổ chức chỉ mục Database:** Sử dụng B+ Tree (biến thể nâng cao của [[Binary Search Tree (BST)|BST]]) để nhóm dữ liệu thành các Block tương thích với phần cứng ổ đĩa SSD/HDD.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Khi nào một hệ thống chấp nhận đánh đổi độ chính xác tuyệt đối để dùng cấu trúc dữ liệu xác suất như Bloom Filter? #card
?
Khi quy mô dữ liệu quá khổng lồ (hàng tỷ bản ghi), việc lưu trữ chính xác tốn hàng trăm GB RAM, và hệ thống chấp nhận một tỷ lệ **dương tính giả cực nhỏ** mà không làm ảnh hưởng đến tính toàn vẹn của nghiệp vụ.
Giải thích sự đánh đổi giữa Read-Heavy và Write-Heavy trong việc đánh chỉ mục (Indexing)? #card
?
Tạo thêm Index giúp tăng tốc độ đọc (Read) từ $O(n) \to O(\log n)$ hoặc $O(1)$, nhưng sẽ làm chậm tốc độ ghi (Write/Insert/Update) vì mỗi thao tác ghi đều buộc phải cập nhật lại toàn bộ cây Index tương ứng.
