---
tags:
  - dsa
  - big-o
  - factorial-time
stage: 1
type: big-o
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - O(n!)
  - Factorial Time
  - Thời gian giai thừa
---

# ☢️ O(n!) - Factorial Time (Thời Gian Giai Thừa)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Big-O Notation - MOC|⚡ Big-O MOC]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
Độ phức tạp phình to theo phép tính giai thừa ($n! = n \times (n-1) \times (n-2) \times \dots \times 1$).
Đây là cấp độ tăng trưởng **khủng khiếp và tồi tệ nhất** trong khoa học máy tính:
- $5! = 120$
- $10! = 3.628.800$ (3,6 triệu)
- $20! = 2.432.902.008.176.640.000$ (2,4 tỷ tỷ phép tính $\to$ siêu máy tính mất hàng thế kỷ).
- Chỉ với $n = 200$, số phép tính vượt xa tổng số giây tính từ vụ nổ Big Bang cho đến nay.

> [!CAUTION]
> **Hình dung sinh động:** Bạn cần xếp thứ tự $n$ người vào $n$ chiếc ghế trên xe buýt. Người thứ nhất có $n$ lựa chọn ghế, người thứ hai có $n-1$ lựa chọn, người thứ ba có $n-2$... Tổng số cách hoán vị chỗ ngồi là $n!$.

---

## 2. Dấu Hiệu Nhận Biết (Code Triggers)
- Các thuật toán duyệt qua **tất cả các hoán vị (Permutations)** của một tập hợp $n$ phần tử.
- Thuật toán sinh hoán vị bằng đệ quy lặp qua các phần tử chưa sử dụng:
  ```typescript
  function permute(nums: number[]): number[][] {
      // Thử từng phần tử làm vị trí đầu tiên và đệ quy với n-1 phần tử còn lại
      return [];
  }
  ```

---

## 3. Thuật Toán & Bài Toán Liên Quan
- Bài toán Người giao hàng duyệt cạn (Traveling Salesperson Problem - TSP Brute-force).
- Bài toán xếp $N$ quân hậu (N-Queens Problem) bản duyệt cạn.
- Sinh toàn bộ hoán vị chuỗi/mảng (String/Array Permutations).

---

## 4. Cách Tối Ưu Thực Tế (Architect's View)
- **Tuyệt đối không chạy Brute-force với $n > 12$:**
- **Chiến lược tiếp cận:**
  1. **Quy hoạch động trạng thái (Bitmask DP):** Đưa bài toán TSP từ $O(n!)$ xuống $O(n^2 \cdot 2^n)$ (thuật toán Held-Karp).
  2. **Thuật toán nhánh cận & Tỉa nhánh (Branch and Bound / Backtracking Pruning):** Dừng ngay nhánh đệ quy khi phát hiện vi phạm điều kiện, không duyệt hết $n!$ trạng thái.
  3. **Thuật toán xấp xỉ & Heuristic (Approximation Algorithms):** Khi $N$ lớn (như tối ưu lộ trình giao hàng Grab/Shopee), ta chấp nhận tìm lời giải *gần tối ưu* (sub-optimal) trong vài giây bằng thuật toán Di truyền (Genetic Algorithm), Luyện kim nhân tạo (Simulated Annealing) hoặc Tìm kiếm cục bộ.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Khi nào một bài toán xuất hiện độ phức tạp $O(n!)$? #card
?
Khi thuật toán buộc phải tạo ra hoặc duyệt qua **tất cả các hoán vị (permutations)** của $n$ phần tử.
Trong thực tế công nghiệp (ví dụ bài toán tìm đường đi giao hàng TSP cho 100 địa điểm), các kỹ sư giải quyết $O(n!)$ như thế nào? #card
?
Không bao giờ giải chính xác bằng Brute-force $O(n!)$. Họ sử dụng các **thuật toán Heuristic / Thuật toán xấp xỉ** (như Genetic Algorithm, Greedy, Ant Colony) để tìm ra đường đi gần tối ưu trong thời gian thực $O(n^2)$ hoặc $O(n \log n)$.
