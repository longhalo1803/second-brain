---
tags:
  - dsa
  - algorithm
  - recursion
  - dynamic-programming
stage: 3
type: algorithm
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Recursion
  - Memoization
  - Đệ quy
  - Ghi nhớ
  - Dynamic Programming
---

# 🔁 Đệ Quy & Ghi Nhớ (Recursion & Memoization)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Đệ quy (Recursion):** Là kỹ thuật một hàm tự gọi lại chính nó với không gian bài toán nhỏ hơn.
- **Cấu trúc 2 phần bắt buộc:**
  1. **Base Case (Điều kiện dừng):** Ngưỡng chặn để hàm dừng lại và trả về giá trị cơ sở, tránh gây ra lỗi `Stack Overflow`.
  2. **Recursive Case (Bước đệ quy):** Chia bài toán lớn thành bài toán con tương tự nhưng có kích thước nhỏ hơn ($n-1, n/2$).
- **Ghi nhớ (Memoization - Top-Down Dynamic Programming):** Lưu lại kết quả của các bài toán con vào một [[Hash Table & HashSet|Hash Table]] hoặc Mảng Cache. Nếu gặp lại trạng thái đó, trả về kết quả ngay trong [[O(1) - Constant Time\|$O(1)$]] thay vì tính lại từ đầu.

---

## 2. Bảng Phép Màu Tối Ưu: Fibonacci Ngây Ngô vs Memoization

```
               fib(5)
             /        \
         fib(4)        fib(3)  <-- Bị tính lại nhiều lần!
        /      \       /     \
    fib(3)   fib(2)  fib(2)  fib(1)
```

| Phiên Bản | Thời Gian (Time Complexity) | Không Gian Bộ Nhớ (Space / Call Stack) |
| :--- | :--- | :--- |
| **Đệ quy thuần (Naive Recursion)** | ☠️ [[O(2^n) - Exponential Time\|$O(2^n)$]] | [[O(n) - Linear Time\|$O(n)$]] |
| **Đệ quy có Memoization (Top-Down DP)** | 🟢 [[O(n) - Linear Time\|$O(n)$]] | [[O(n) - Linear Time\|$O(n)$]] |
| **Quy hoạch động vòng lặp (Bottom-Up DP)** | 🟢 [[O(n) - Linear Time\|$O(n)$]] | 🟢 [[O(1) - Constant Time\|$O(1)$]] (chỉ lưu 2 biến) |

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
2 thành phần bắt buộc của bất kỳ hàm đệ quy nào là gì? #card
?
1. **Base Case (Điều kiện dừng)** để chặn đệ quy vô tận.
2. **Recursive Case (Lời gọi đệ quy)** chia nhỏ bài toán.
Memoization biến đổi bài toán đệ quy như thế nào? #card
?
Nó dùng thêm một bảng tra cứu (**Lookup Table / Cache**) để lưu lại kết quả của từng bài toán con, triệt tiêu việc tính toán lặp lại và giảm độ phức tạp thời gian từ mũ ($O(2^n)$) xuống tuyến tính ($O(n)$).
