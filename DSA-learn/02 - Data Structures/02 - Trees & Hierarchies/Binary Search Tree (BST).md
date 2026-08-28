---
tags:
  - dsa
  - data-structure
  - tree
stage: 4
type: data-structure
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - BST
  - Binary Search Tree
  - Self-balancing Binary Search Tree
  - Cây tìm kiếm nhị phân
---

# 🌲 Cây Tìm Kiếm Nhị Phân (Binary Search Tree - BST)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Quy tắc bất biến (BST Property):** 
  - Mọi nút ở **Cây con bên Trái** đều có giá trị **nhỏ hơn** nút cha (`Left < Root`).
  - Mọi nút ở **Cây con bên Phải** đều có giá trị **lớn hơn** nút cha (`Right > Root`).
- **Hình dung:** Giống như cấu trúc phân nhánh cây gia phả hoặc hệ thống thư mục File Explorer. Khi đứng ở một nút, bạn biết chính xác cần rẽ trái hay rẽ phải để tìm dữ liệu mong muốn.

---

## 2. Bảng Độ Phức Tạp (Complexity Sheet)

| Thao Tác | BST Cân Bằng (Balanced BST) | BST Bị Lệch (Degenerate / Skewed) | Ghi Chú |
| :--- | :--- | :--- | :--- |
| **Tìm kiếm (Search)** | [[O(log n) - Logarithmic Time\|$O(\log n)$]] | [[O(n) - Linear Time\|$O(n)$]] | Phụ thuộc chiều cao cây ($h$) |
| **Chèn (Insert)** | [[O(log n) - Logarithmic Time\|$O(\log n)$]] | [[O(n) - Linear Time\|$O(n)$]] | Đi theo nhánh tới lá |
| **Xóa (Delete)** | [[O(log n) - Logarithmic Time\|$O(\log n)$]] | [[O(n) - Linear Time\|$O(n)$]] | Cần thay thế bằng In-order Successor |
| **Bộ nhớ (Space)** | [[O(n) - Linear Time\|$O(n)$]] | [[O(n) - Linear Time\|$O(n)$]] | Lưu trữ các con trỏ `left`, `right` |

---

## 3. Cạm Bẫy Lệch Nhánh & Cây Tự Cân Bằng (Self-Balancing Trees)

> [!WARNING]
> **Edge Case chí mạng:** Nếu bạn chèn các số **đã được sắp xếp sẵn** (ví dụ: `1, 2, 3, 4, 5`) vào một cây BST ngây ngô, cây sẽ mọc dài thành một đường thẳng (thoái hóa thành [[Linked List]]), khiến mọi thao tác từ $O(\log n)$ sụp đổ về $O(n)$!

- **Giải pháp của Kiến trúc sư:** Sử dụng **Cây tự cân bằng** (Self-Balancing BST) như **AVL Tree** hoặc **Red-Black Tree** (sử dụng phép quay cây Tree Rotations để luôn giữ độ cao $h \approx \log_2 n$).
- **Ứng dụng công nghiệp:** `std::map` và `std::set` trong C++, `TreeMap` và `TreeSet` trong Java đều được xây dựng dựa trên Red-Black Tree.

---

## 4. Sự Đánh Đổi: [[Hash Table & HashSet|Hash Table]] vs BST

| Tiêu Chí | Hash Table | Balanced BST (Red-Black Tree) |
| :--- | :--- | :--- |
| **Tốc độ tra cứu điểm (Point Lookup)** | 🟢 $O(1)$ | 🟡 $O(\log n)$ |
| **Dữ liệu có thứ tự (Order Maintenance)** | 🔴 Không có | 🟢 Có thứ tự (In-order traversal ra mảng tăng dần) |
| **Tìm kiếm khoảng (Range Queries `[A..B]`)** | 🔴 Chậm ($O(n)$ phải duyệt hết) | 🟢 Rất nhanh ($O(\log n + k)$) |
| **Tìm phần tử Min / Max** | 🔴 $O(n)$ | 🟢 $O(\log n)$ (hoặc $O(1)$) |

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Quy tắc cốt lõi của Binary Search Tree (BST) là gì? #card
?
Với mọi node: **Tất cả các node ở cây con bên trái < Node hiện tại < Tất cả các node ở cây con bên phải**.
Khi nào nên chọn Red-Black Tree / BST thay vì Hash Table? #card
?
Khi cần dữ liệu **luôn được duy trì thứ tự sắp xếp**, hoặc cần thực hiện các truy vấn **tìm kiếm theo khoảng (Range Queries: từ X đến Y)** hay tìm phần tử lớn nhất/nhỏ nhất.
