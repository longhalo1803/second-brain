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
  - Selection Sort
  - Sắp xếp chọn
---

# 🎯 Sắp Xếp Chọn (Selection Sort)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Ý tưởng:** Ở mỗi lượt duyệt, tìm phần tử nhỏ nhất (Min) trong đoạn chưa sắp xếp, sau đó hoán đổi nó với phần tử ở đầu đoạn đó.
- **Độ phức tạp:**
  - Luôn luôn là [[O(n^2) - Quadratic Time\|$O(n^2)$]] trong cả Best, Average và Worst case vì bắt buộc phải quét hết mảng để tìm Min.
  - Space: [[O(1) - Constant Time\|$O(1)$]] (In-place).
- **Điểm đặc biệt:** Số lần hoán đổi (Swaps) tối đa chỉ là $O(n)$, ít hơn Bubble Sort.
