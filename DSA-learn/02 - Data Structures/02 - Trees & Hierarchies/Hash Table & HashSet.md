---
tags:
  - dsa
  - data-structure
  - hash
stage: 4
type: data-structure
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Hash Table
  - Hash Map
  - Hash Set
  - Hashmaps
  - Hashset
  - Bảng băm
  - Tập hợp băm
---

# ⚡ Bảng Băm & Tập Hợp Băm (Hash Table & HashSet)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Định nghĩa:** Là cấu trúc dữ liệu lưu trữ dưới dạng cặp **Key - Value** (hoặc chỉ Key đối với HashSet). Nó sử dụng một **Hàm băm (Hash Function)** để biến một chuỗi hoặc đối tượng tùy ý thành một chỉ số số nguyên (Integer Index) trỏ thẳng vào mảng RAM bên dưới.
- **"Vua" tìm kiếm:** Biến thao tác tìm kiếm từ $O(n)$ thành [[O(1) - Constant Time\|$O(1)$]] tức thì.
- **Xử lý va chạm (Collision Resolution):** Khi 2 key khác nhau sinh ra cùng 1 index:
  - *Chaining (Separate Chaining):* Mỗi ô mảng là một [[Linked List]] lưu các cặp trùng hash.
  - *Open Addressing:* Tìm ô trống tiếp theo trong mảng (Linear Probing).

---

## 2. Bảng Độ Phức Tạp (Complexity Sheet)

| Thao Tác | Trung Bình (Average) | Xấu Nhất (Worst Case - Trùng Hash toàn bộ) | Không Gian (Space) |
| :--- | :--- | :--- | :--- |
| **Tra cứu (Lookup / Get)** | [[O(1) - Constant Time\|$O(1)$]] | [[O(n) - Linear Time\|$O(n)$]] | [[O(n) - Linear Time\|$O(n)$]] |
| **Chèn (Insert / Put)** | [[O(1) - Constant Time\|$O(1)$]] | [[O(n) - Linear Time\|$O(n)$]] | [[O(n) - Linear Time\|$O(n)$]] |
| **Xóa (Delete / Remove)** | [[O(1) - Constant Time\|$O(1)$]] | [[O(n) - Linear Time\|$O(n)$]] | [[O(n) - Linear Time\|$O(n)$]] |

---

## 3. Sự Đánh Đổi (Trade-offs) Cốt Lõi

- 🟢 **Điểm mạnh (Superpower):**
  - Tốc độ đọc/ghi chớp nhoáng $O(1)$.
  - Là công cụ số 1 để giải cứu các thuật toán chậm $O(n^2)$ hoặc $O(2^n)$ bằng kỹ thuật **Đánh đổi RAM lấy Tốc độ**.
- 🔴 **Điểm yếu (Weakness):**
  - **Không có thứ tự:** Dữ liệu được băm rải rác, không hỗ trợ tìm kiếm khoảng (Range Queries) như [[Binary Search Tree (BST)|BST]] hay B-Tree.
  - **Tốn bộ nhớ:** Cần giữ hệ số tải (Load Factor) thấp ($\approx 0.7$) để tránh đụng độ, nghĩa là mảng bộ nhớ bên dưới luôn phải để trống $30\% - 50\%$.

---

## 4. Ứng Dụng Thực Tế & Thiết Kế Hệ Thống
- **Caching Systems:** Redis, Memcached, [[LRU Cache]].
- **Database Indexing:** Hash Indexes trong MySQL/PostgreSQL (chỉ dùng cho so sánh bằng `=`, không dùng cho `<, >`).
- **Khử trùng lặp (Deduplication):** Dùng `HashSet` để kiểm tra tài khoản hoặc email đã tồn tại chưa trong $O(1)$.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Cơ chế nào giúp Hash Table đạt tốc độ tra cứu $O(1)$? #card
?
Hàm băm (**Hash Function**) chuyển đổi Key thành vị trí ô nhớ Index trong mảng nền, máy tính nhảy thẳng tới địa chỉ ô nhớ đó trong $O(1)$ mà không cần duyệt so sánh.
Khi nào Hash Table bị thoái hóa về $O(n)$? #card
?
Khi tất cả các Key đều bị đụng độ (Collision) và băm vào cùng một ô nhớ duy nhất, biến Bucket thành một Linked List dài $N$ phần tử.
