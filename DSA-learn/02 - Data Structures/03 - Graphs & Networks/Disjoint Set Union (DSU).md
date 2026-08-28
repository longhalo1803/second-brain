---
tags:
  - dsa
  - data-structure
  - graph
  - dsu
stage: 6
type: data-structure
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Disjoint Set
  - Union Find
  - DSU
  - Disjoint Set Union (DSU)
  - Tập hợp rời rạc
---

# 🔗 Tập Hợp Rời Rạc & Union-Find (Disjoint Set Union - DSU)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Mục tiêu:** Quản lý một tập hợp các phần tử được chia thành các nhóm (tập hợp) không giao nhau.
- **2 Thao tác chính:**
  1. `find(x)`: Tìm đại diện (Root Leader) của nhóm chứa phần tử $x$.
  2. `union(x, y)`: Hợp nhất hai nhóm chứa $x$ và $y$ lại thành một nhóm duy nhất.

---

## 2. 2 Kỹ Thuật Tối Ưu "Thần Thánh" (Path Compression & Union by Rank)
- **Nén đường đi (Path Compression):** Trong quá trình `find(x)`, gán trực tiếp cha của mọi nút trên đường đi về thẳng nút gốc (Root Leader).
- **Hợp nhất theo thứ hạng (Union by Rank / Size):** Luôn gắn cây thấp hơn vào gốc của cây cao hơn để hạn chế chiều cao cây.
- **Độ phức tạp siêu việt:** Với cả 2 kỹ thuật trên, mỗi thao tác chỉ mất thời gian **$O(\alpha(n))$** (hàm Ackermann nghịch đảo), với mọi $n \le 10^{80}$ thì $\alpha(n) \le 4 \approx O(1)$!

---

## 3. Ứng Dụng Thực Tế
- Kiểm tra **Chu trình trong đồ thị vô hướng** (Cycle Detection).
- Thuật toán **Kruskal** tìm Cây khung nhỏ nhất (Minimum Spanning Tree - MST).
- Đếm số lượng thành phần liên thông trong mạng xã hội (VD: Tìm nhóm bạn bè liên kết).
