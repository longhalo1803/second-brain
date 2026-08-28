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
  - Bubble Sort
  - Sắp xếp nổi bọt
---

# 🫧 Sắp Xếp Nổi Bọt (Bubble Sort)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Ý tưởng:** Liên tục so sánh 2 phần tử liền kề nhau (`arr[i]` và `arr[i+1]`), nếu sai thứ tự thì hoán đổi (swap). Sau mỗi lượt duyệt, phần tử lớn nhất sẽ "nổi bọt" về cuối mảng.
- **Độ phức tạp:**
  - Worst & Average: [[O(n^2) - Quadratic Time\|$O(n^2)$]] (2 vòng lặp lồng nhau).
  - Best Case (khi mảng đã sắp xếp và có cờ `swapped`): [[O(n) - Linear Time\|$O(n)$]].
  - Space: [[O(1) - Constant Time\|$O(1)$]] (In-place).
- **Ứng dụng:** Chủ yếu dùng trong giảng dạy học thuật để hiểu bản chất so sánh cặp; **không bao giờ dùng trong hệ thống thực tế** vì quá chậm so với [[Quick Sort]] hay [[Merge Sort]].
