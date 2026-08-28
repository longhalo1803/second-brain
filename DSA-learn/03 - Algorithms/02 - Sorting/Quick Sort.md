---
tags:
  - dsa
  - algorithm
  - sorting
  - divide-and-conquer
stage: 5
type: algorithm
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Quick Sort
  - Sắp xếp nhanh
---

# ⚡ Sắp Xếp Nhanh (Quick Sort)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Tư tưởng Phân Vùng (Partitioning):**
  1. Chọn một phần tử làm chốt (**Pivot**).
  2. Phân vùng mảng: Dồn tất cả phần tử **nhỏ hơn Pivot** sang bên trái, tất cả phần tử **lớn hơn Pivot** sang bên phải. Lúc này, Pivot đã đứng chính xác ở vị trí cuối cùng của nó trong mảng đã sắp xếp.
  3. Đệ quy sắp xếp 2 nửa trái và phải.
- **Hoạt động Tại Chỗ (In-place):** Không cần mảng phụ trợ.

---

## 2. Bảng Độ Phức Tạp (Complexity Analysis)

| Trường Hợp | Thời Gian (Time) | Không Gian Bộ Nhớ (Space / Call Stack) |
| :--- | :--- | :--- |
| **Tốt nhất (Best Case - Pivot chia đôi mảng)** | [[O(n log n) - Linearithmic Time\|$O(n \log n)$]] | [[O(log n) - Logarithmic Time\|$O(\log n)$]] |
| **Trung bình (Average)** | [[O(n log n) - Linearithmic Time\|$O(n \log n)$]] | [[O(log n) - Logarithmic Time\|$O(\log n)$]] |
| **Xấu nhất (Worst Case - Pivot là Min/Max liên tục)**| [[O(n^2) - Quadratic Time\|$O(n^2)$]] | [[O(n) - Linear Time\|$O(n)$]] |

---

## 3. Bí Quyết Của Kiến Trúc Sư: Tránh Bẫy $O(n^2)$
- Nếu chọn Pivot ngây ngô (luôn chọn phần tử đầu hoặc cuối) trên một mảng **đã sắp xếp sẵn**, Quick Sort sẽ thoái hóa thành $O(n^2)$.
- **Giải pháp:** 
  - **Randomized Quick Sort:** Chọn Pivot ngẫu nhiên.
  - **Median-of-Three:** Chọn trung vị của 3 phần tử (Đầu, Giữa, Cuối) làm Pivot.
  - **Introsort:** Kết hợp Quick Sort $\to$ Heap Sort nếu đệ quy quá sâu (chuẩn của C++ `std::sort`).

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao Quick Sort thường chạy nhanh hơn Merge Sort trong thực tế dù worst-case là $O(n^2)$? #card
?
Vì Quick Sort chạy **In-place** (không tốn chi phí cấp phát RAM mới) và có **Cache Locality** tuyệt vời, hệ số hằng số ẩn (Hidden Constant Factor) nhỏ hơn nhiều so với Merge Sort.
Kỹ thuật nào giúp triệt tiêu nguy cơ rơi vào $O(n^2)$ của Quick Sort? #card
?
Chọn Pivot ngẫu nhiên (**Randomized Pivot**) hoặc chọn trung vị của 3 phần tử (**Median of Three**).
