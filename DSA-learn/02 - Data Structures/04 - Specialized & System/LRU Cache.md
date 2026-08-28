---
tags:
  - dsa
  - data-structure
  - system-design
  - cache
stage: 6
type: data-structure
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - LRU Cache
  - Least Recently Used
  - Bộ nhớ đệm LRU
---

# 🔄 Bộ Nhớ Đệm LRU (LRU Cache - Least Recently Used)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Chiến lược loại bỏ:** **LRU (Least Recently Used)** — Khi bộ nhớ đệm (Cache) bị đầy giới hạn dung lượng ($Capacity$), hệ thống sẽ tự động vứt bỏ phần tử **ít được sử dụng nhất trong thời gian dài nhất** để nhường chỗ cho dữ liệu mới.
- **Yêu cầu kỹ thuật khắc nghiệt:** Cả 2 thao tác `get(key)` (đọc) và `put(key, value)` (ghi/cập nhật) **bắt buộc phải chạy trong [[O(1) - Constant Time\|$O(1)$]]**.

---

## 2. Kiến Trúc Kết Hợp "Thần Thánh": Hash Table + Doubly Linked List

Để đạt được tốc độ $O(1)$ cho mọi thao tác, LRU Cache kết hợp 2 cấu trúc dữ liệu kinh điển:

```
[Hash Table (Key -> Node Pointer)]
       |              |
       v              v
[Head (Most Recent)] <-> [Node A] <-> [Node B] <-> [Tail (Least Recent)]
```

1. **[[Hash Table & HashSet|Hash Table]] ($O(1)$):** Lưu trữ ánh xạ từ `Key` tới thẳng `Địa chỉ Node` trong RAM để tìm vị trí node tức thì.
2. **[[Linked List|Doubly Linked List]] ($O(1)$):** Duy trì thứ tự truy cập theo thời gian:
   - Node ở đầu (`Head`) là phần tử **vừa mới được dùng gần nhất** (Most Recently Used).
   - Node ở đuôi (`Tail`) là phần tử **ít được dùng nhất** (Least Recently Used).
   - Khi một node được truy cập (`get` hoặc `put`), ta ngắt kết nối và chuyển node đó lên `Head` trong $O(1)$.
   - Khi cache đầy, ta ngắt node ở `Tail` và xóa key khỏi Hash Table trong $O(1)$.

---

## 3. Ứng Dụng Thực Tế Trong Công Nghiệp
- **Hệ điều hành:** Quản lý Page Replacement trong Bộ nhớ ảo (Virtual Memory).
- **Trình duyệt Web:** Cache các tài nguyên hình ảnh/CSS tải gần nhất.
- **Cơ sở dữ liệu & Backend:** Buffer Pool trong InnoDB (MySQL), tầng Caching bộ nhớ ứng dụng.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao LRU Cache lại phải kết hợp cả Hash Table và Doubly Linked List? #card
?
- **Hash Table** giúp tìm kiếm và trỏ tới node trong **$O(1)$**.
- **Doubly Linked List** giúp xóa node bất kỳ và đẩy lên đầu (cập nhật thứ tự sử dụng) trong **$O(1)$**.
Khi cache đầy và cần chèn thêm phần tử mới, node ở vị trí nào sẽ bị loại bỏ? #card
?
Node nằm ở **đuôi (Tail)** của Doubly Linked List (phần tử Least Recently Used).
