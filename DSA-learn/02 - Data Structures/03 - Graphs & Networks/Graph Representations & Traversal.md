---
tags:
  - dsa
  - data-structure
  - graph
stage: 6
type: data-structure
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Graph
  - Graphs
  - Đồ thị
  - BFS
  - DFS
  - Graph BFS / DFS Patterns
  - Duyệt đồ thị BFS và DFS
---

# 🕸️ Đồ Thị & Kỹ Thuật Duyệt (Graph Representations & Traversal)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Định nghĩa:** Đồ thị là tập hợp các **Đỉnh (Vertices / Nodes)** và các **Cạnh (Edges)** nối các đỉnh lại với nhau. Nó mô tả các mối quan hệ mạng lưới phi tuyến tính, chằng chịt và không có nút gốc cố định.
- **Phân loại:**
  - Có hướng (Directed) vs Vô hướng (Undirected).
  - Có trọng số (Weighted) vs Không trọng số (Unweighted).
  - Có chu trình (Cyclic) vs Không chu trình (DAG - Directed Acyclic Graph).

---

## 2. So Sánh 2 Cách Biểu Diễn Đồ Thị Trong RAM

| Tiêu Chí | Ma Trận Kề (Adjacency Matrix) | Danh Sách Kề (Adjacency List) |
| :--- | :--- | :--- |
| **Cấu trúc lưu trữ** | Mảng 2 chiều $V \times V$ boolean/int | Mảng gồm $V$ danh sách con / [[Hash Table & HashSet\|Hash Table]] |
| **Không gian bộ nhớ (Space)** | 🔴 [[O(n^2) - Quadratic Time\|$O(V^2)$]] (rất tốn RAM) | 🟢 **$O(V + E)$** (tiết kiệm) |
| **Kiểm tra xem $u$ và $v$ có nối nhau không** | 🟢 $O(1)$ | 🟡 $O(\text{bậc của } u)$ |
| **Duyệt tất cả hàng xóm của đỉnh $u$** | 🔴 $O(V)$ (phải quét cả hàng) | 🟢 $O(\text{bậc của } u)$ |
| **Khi nào nên dùng?** | Khi đồ thị dày đặc cạnh ($E \approx V^2$) | Khi đồ thị thưa thớt cạnh ($E \ll V^2$ - Đa số thực tế) |

---

## 3. Hai Thuật Toán Duyệt Đồ Thị Cơ Bản

### 1. BFS (Breadth-First Search - Duyệt Theo Chiều Rộng)
- **Cơ chế:** Dùng [[Queue & Deque|Hàng đợi (Queue)]]. Loan ra theo từng gợn sóng từ gần đến xa.
- **Đặc tính siêu việt:** Tìm **đường đi ngắn nhất** trên đồ thị không có trọng số (hoặc trọng số bằng nhau).
- **Độ phức tạp:** $O(V + E)$ Time, $O(V)$ Space.

### 2. DFS (Depth-First Search - Duyệt Theo Chiều Sâu)
- **Cơ chế:** Dùng [[Stack|Ngăn xếp (Stack)]] hoặc [[Recursion & Memoization|Đệ quy]]. Đâm thẳng một mạch tới ngõ cụt rồi mới quay lui (Backtracking).
- **Đặc tính siêu việt:** Kiểm tra chu trình, sắp xếp Topo (Topological Sort), tìm thành phần liên thông mạnh.
- **Độ phức tạp:** $O(V + E)$ Time, $O(V)$ Space (Call stack).

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Khi nào nên dùng BFS thay vì DFS? #card
?
Khi cần tìm **đường đi ngắn nhất (Shortest Path)** hoặc mức độ khoảng cách tối thiểu giữa 2 đỉnh trên đồ thị không trọng số.
Tại sao trong thực tế hầu hết hệ thống (như Facebook/Google Maps) dùng Adjacency List thay vì Adjacency Matrix? #card
?
Vì đồ thị thực tế rất thưa thớt (Sparse Graph). Nếu Facebook có 3 tỷ người, Ma trận kề cần $(3 \times 10^9)^2$ ô nhớ (hàng triệu TB RAM), trong khi Danh sách kề chỉ lưu đúng các cạnh bạn bè thực tế ($O(V + E)$).
