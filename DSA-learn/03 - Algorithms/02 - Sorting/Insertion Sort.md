---
tags:
  - dsa
  - algorithm
  - sorting
stage: 3
type: algorithm
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Insertion Sort
  - Sắp xếp chèn
---

# 🃏 Sắp Xếp Chèn (Insertion Sort)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Ý tưởng:** Giống như cách bạn xếp các lá bài tây trên tay khi chơi bài: Lấy từng lá bài mới, so sánh và chèn nó vào đúng vị trí trong tập các lá bài đã được sắp xếp bên tay trái.
- **Độ phức tạp:**
  - Worst & Average: [[O(n^2) - Quadratic Time\|$O(n^2)$]].
  - Best Case (khi mảng đã gần như sắp xếp hoàn chỉnh): 🟢 [[O(n) - Linear Time\|$O(n)$]].
  - Space: [[O(1) - Constant Time\|$O(1)$]] (In-place).
- **Ứng dụng thực tế:** Được các thuật toán hybrid hiện đại (như **Timsort** trong Python/Java, **Introsort** trong C++) sử dụng khi kích thước mảng con nhỏ ($N \le 32$ hoặc $N \le 64$) vì tốc độ thực thi rất nhanh và chi phí hằng số cực nhỏ.
