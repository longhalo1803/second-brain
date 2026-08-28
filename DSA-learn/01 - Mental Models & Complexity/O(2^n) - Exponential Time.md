---
tags:
  - dsa
  - big-o
  - exponential-time
stage: 1
type: big-o
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - O(2^n)
  - Exponential Time
  - Thời gian lũy thừa
---

# ☠️ O(2^n) - Exponential Time (Thời Gian Lũy Thừa)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Big-O Notation - MOC|⚡ Big-O MOC]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
Mỗi khi bạn thêm **đúng 1 phần tử dữ liệu mới** ($n \to n+1$), khối lượng công việc và thời gian xử lý **tăng gấp đôi ($2\times$)**.
Với $n = 10$, số bước là $1.024$. Với $n = 30$, số bước là $1.073.741.824$ (hơn 1 tỷ phép tính). Với $n = 100$, số bước lớn hơn tổng số nguyên tử trong vũ trụ quan sát được.

> [!CAUTION]
> **Hình dung sinh động:** Trò chơi tung $n$ đồng xu. 1 đồng xu có 2 khả năng (Sấp/Ngửa). Thêm đồng thứ 2, có 4 trường hợp. Thêm đồng thứ 3, có 8 trường hợp... Mỗi đồng xu thêm vào làm số kịch bản nhân đôi ngay lập tức.

---

## 2. Dấu Hiệu Nhận Biết (Code Triggers)
- Hàm đệ quy gọi lại chính nó **hai lần** trên mỗi nhánh mà không có kỹ thuật lưu nhớ (Memoization):
  ```typescript
  function fibonacci(n: number): number {
      if (n <= 1) return n;
      return fibonacci(n - 1) + fibonacci(n - 2);
  }
  ```
- Các thuật toán duyệt vét cạn mọi tập con (Power Set) của một tập hợp $n$ phần tử ($2^n$ tập con).
- Bài toán giải mã mật khẩu brute-force thử mọi chuỗi nhị phân độ dài $n$.

---

## 3. Thuật Toán & Bài Toán Liên Quan
- Đệ quy Fibonacci ngây ngô (Naive Fibonacci).
- Bài toán cái túi (0/1 Knapsack Problem) bản duyệt cạn.
- Sinh tất cả các tập hợp con (Subsets generation / Combinations).
- Thuật toán quay lui vét cạn (Backtracking không có tỉa nhánh).

---

## 4. Cách Tối Ưu Thực Tế (Architect's View)
- **Cấm kỵ trong hệ thống thực tế:** Thuật toán $O(2^n)$ không thể chạy với $n > 40$.
- **Vũ khí cứu cánh — [[Recursion & Memoization|Quy Hoạch Động (Dynamic Programming) & Memoization]]:**
  - Trong cây đệ quy của Fibonacci, cùng một bài toán con (ví dụ `fib(5)`) bị tính đi tính lại hàng triệu lần.
  - Sử dụng một mảng hoặc [[Hash Table & HashSet|Hash Table]] để lưu kết quả đã tính (Memoization) $\to$ Giảm thời gian từ $O(2^n)$ ngoạn mục xuống còn $O(n)$!

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao đệ quy Fibonacci ngây ngô lại có độ phức tạp $O(2^n)$? #card
?
Vì mỗi nút trên cây đệ quy sinh ra 2 nhánh con, tạo thành một cây nhị phân có độ sâu $n$, tổng số nút trên cây là $2^0 + 2^1 + \dots + 2^n \approx 2^{n+1}-1 = O(2^n)$.
Kỹ thuật nào giúp biến thuật toán đệ quy $O(2^n)$ thành $O(n)$? #card
?
**Dynamic Programming (Quy hoạch động) / Memoization (Ghi nhớ)** — Lưu lại kết quả của các bài toán con đã giải để không bao giờ phải tính lại lần thứ hai.
