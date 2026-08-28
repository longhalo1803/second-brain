---
tags:
  - dsa
  - big-o
  - linear-time
stage: 1
type: big-o
status: completed
created: 2026-08-24
updated: 2026-08-27
aliases:
  - O(n)
  - Linear Time
  - Thời gian tuyến tính
---

# 🟡 O(n) - Linear Time (Thời Gian Tuyến Tính)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Big-O Notation - MOC|⚡ Big-O MOC]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
Quy mô dữ liệu đầu vào $n$ tăng bao nhiêu lần, thời gian xử lý hoặc số lượng phép tính tăng **tương ứng bấy nhiêu lần** theo tỷ lệ $1:1$. Nếu $n = 100$, mất 100 bước; nếu $n = 10.000$, mất 10.000 bước.

> [!TIP]
> **Hình dung sinh động:** Bạn đánh rơi chiếc nhẫn trên một bờ biển trải dài 10km. Vì không biết vị trí, bạn buộc phải đi bộ mò mẫm, quét mắt nhìn từng mét vuông cát một từ đầu bãi đến cuối bãi. Bờ biển dài gấp đôi, thời gian tìm kiếm tăng gấp đôi.

---

## 2. Dấu Hiệu Nhận Biết (Code Triggers)
- Xuất hiện **1 vòng lặp đơn** duyệt qua toàn bộ $n$ phần tử của tập dữ liệu: `for (int i = 0; i < n; i++)`.
- Các thao tác sao chép mảng, tìm giá trị Max/Min trong mảng chưa sắp xếp, tính tổng các phần tử.
- Duyệt qua một danh sách liên kết từ đầu đến cuối (`while node != null`).

---

## 3. Cấu Trúc Dữ Liệu & Thuật Toán Liên Quan
- [[Linear Search|Tìm kiếm tuyến tính (Linear Search)]] trên mảng chưa sắp xếp.
- [[Array & Dynamic Array|Mảng (Arrays)]]: Thao tác chèn/xóa phần tử ở giữa hoặc đầu mảng (do phải dịch chuyển $O(n)$ phần tử còn lại).
- [[Linked List|Danh sách liên kết (Linked Lists)]]: Tìm kiếm một giá trị hoặc truy cập phần tử thứ $k$.
- Các thuật toán dùng Pattern tối ưu như [[Two Pointers Pattern|Hai con trỏ]] và [[Sliding Window Pattern|Cửa sổ trượt]] khi duyệt mảng một lượt.

---

## 4. Cách Tối Ưu Thực Tế (Architect's View)
- $O(n)$ là mức độ phức tạp **chấp nhận được** đối với các tác vụ xử lý hàng loạt (Batch Processing) hoặc với tập dữ liệu vừa phải.
- Tuy nhiên, trong các hệ thống thời gian thực (Real-time Web Services) có tần suất đọc dữ liệu cực lớn (Read-heavy), việc quét $O(n)$ trên hàng triệu bản ghi cho mỗi request sẽ làm nghẽn CPU.
- **Chiến lược cứu viện:** Chuyển đổi dữ liệu sang [[Hash Table & HashSet|Hash Table]] để đưa việc tra cứu về $O(1)$, hoặc xây dựng cấu trúc cây tự cân bằng (Indexing) để đưa về $O(\log n)$.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Dấu hiệu nhận biết code chạy ở mức $O(n)$ là gì? #card
?
Một vòng lặp đơn chạy tuần tự qua toàn bộ $n$ phần tử của dữ liệu đầu vào mà không có bước nhảy cấp số nhân hay chia đôi phạm vi.
Tại sao thao tác chèn/xóa ở đầu mảng (Array) lại mất $O(n)$ trong khi Linked List chỉ mất $O(1)$? #card
?
Vì các phần tử của Mảng nằm liên tiếp trong bộ nhớ, khi xóa/chèn ở đầu, máy tính phải dịch chuyển toàn bộ $n-1$ phần tử còn lại sang vị trí mới. Linked List chỉ cần cập nhật lại con trỏ `head`.
