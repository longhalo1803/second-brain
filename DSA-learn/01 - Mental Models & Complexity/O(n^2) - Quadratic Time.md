---
tags:
  - dsa
  - big-o
  - quadratic-time
stage: 1
type: big-o
status: completed
created: 2026-08-24
updated: 2026-08-27
aliases:
  - O(n^2)
  - Quadratic Time
  - Thời gian bậc hai
---

# 🔴 O(n^2) - Quadratic Time (Thời Gian Bậc Hai)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Big-O Notation - MOC|⚡ Big-O MOC]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
Khi lượng dữ liệu $n$ tăng gấp 10 lần, thời gian xử lý hoặc số lượng phép tính tăng vọt lên **100 lần** (theo cấp số nhân bình phương $n^2$). Nếu $n = 1.000$, số bước là $1.000.000$. Nếu $n = 100.000$, số bước là $10.000.000.000$ (10 tỷ phép tính $\to$ treo máy).

> [!TIP]
> **Hình dung sinh động:** Buổi tiệc kết bạn (Speed Dating) cho 100 người. Bạn bắt buộc **từng người** trong căn phòng phải lần lượt ngồi xuống trò chuyện và bắt tay với **tất cả những người còn lại**. Tổng số lượt bắt tay sẽ là $\frac{n(n-1)}{2} \approx \frac{100 \times 100}{2} = 5.000$ lượt!

---

## 2. Dấu Hiệu Nhận Biết (Code Triggers)
- **Hai vòng lặp lồng nhau (Nested Loops)** phụ thuộc vào biến $n$:
  ```typescript
  for (let i = 0; i < n; i++) {
      for (let j = 0; j < n; j++) {
          // Xử lý từng cặp (i, j)
      }
  }
  ```
- Các thuật toán duyệt vét cạn toàn bộ các cặp đôi phần tử trong danh sách (Pairwise comparisons).

---

## 3. Cấu Trúc Dữ Liệu & Thuật Toán Liên Quan
- Thuật toán sắp xếp cơ bản duyệt trâu: `[[Bubble Sort]]`, `[[Selection Sort]]`, `[[Insertion Sort]]`.
- Các bài toán tìm kiếm cặp phần tử có tổng bằng $K$ (Two Sum bản Brute-force).
- Ma trận $N \times N$: Khởi tạo hoặc duyệt qua toàn bộ các ô trong bảng 2 chiều.

---

## 4. Cách Tối Ưu Thực Tế (Architect's View)
- **Báo Động Đỏ (Red Flag):** Trong các ứng dụng sản xuất (Production), thấy code chạy ở mức $O(n^2)$ trên dữ liệu người dùng là nguy cơ tiềm tàng gây sập server (DDoS chính mình).
- **Chiến Lược Giải Cứu:**
  1. **Đánh đổi RAM lấy Tốc độ:** Dùng [[Hash Table & HashSet|Hash Table]] ($O(n)$ Space) để nhớ các giá trị của vòng lặp thứ nhất, triệt tiêu vòng lặp lồng thứ hai $\to$ Đưa về $O(n)$ Time (ví dụ: Giải bài Two Sum trong $O(n)$).
  2. **Sắp xếp trước rồi dùng Two Pointers:** Sắp xếp mảng mất $O(n \log n)$, sau đó áp dụng [[Two Pointers Pattern|Hai con trỏ]] mất $O(n)$ $\to$ Tổng thời gian là $O(n \log n)$, nhanh hơn rất nhiều so với $O(n^2)$.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Khi gặp thuật toán $O(n^2)$ do 2 vòng lặp lồng nhau, 2 chiến lược tối ưu phổ biến nhất là gì? #card
?
1. Dùng **Hash Table** để tra cứu trong $O(1)$, giảm thời gian xuống $O(n)$ (đánh đổi $O(n)$ Space).
2. **Sắp xếp** mảng trong $O(n \log n)$ rồi dùng kỹ thuật **Two Pointers** trong $O(n)$, tổng thời gian là $O(n \log n)$ và giữ $O(1)$ Space.
