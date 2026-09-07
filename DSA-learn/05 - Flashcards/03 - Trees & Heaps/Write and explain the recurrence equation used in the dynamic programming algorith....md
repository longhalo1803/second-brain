---
title: "Write and explain the recurrence equation used in the dynamic programming algorith..."
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Write and explain the recurrence equation used in the dynamic programming algorith..."
---

# 🎴 Write and explain the recurrence equation used in the dynamic programming algorith...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ Write and explain the recurrence equation used in the dynamic programming algorithm for computing all-pairs shortest path costs in a graph $G$ with weighted edges (Floyd-Warshall algorithm). Discuss the correctness of the equation. #card

?

- **Subproblem Definition:**
  Let the vertices be indexed from $1$ to $n$, so $V = \{1, 2, \dots, n\}$.
  Define $d_{ij}^{(k)}$ as the weight of the shortest path from $i$ to $j$ such that all intermediate vertices on the path belong exclusively to the subset $\{1, 2, \dots, k\}$.
- **Recurrence Equation:**
- **Base Case ($k=0$):** No intermediate nodes are permitted. The path can only consist of the direct edge:

$$

d\_{ij}^{(0)} = \begin{cases}
0 & \text{if } i = j \\
w(i, j) & \text{if } i \ne j \text{ and } (i, j) \in E \\
\infty & \text{if } i \ne j \text{ and } (i, j) \notin E
\end{cases}

$$

- **Recursive Step ($k \ge 1$):**

$$

d*{ij}^{(k)} = \min \left( d*{ij}^{(k-1)}, \; d*{ik}^{(k-1)} + d*{kj}^{(k-1)} \right)

$$

- **Explanation and Correctness Discussion:**
  Consider a shortest path $p$ from $i$ to $j$ whose intermediate nodes belong to $\{1, \dots, k\}$. Regarding vertex $k$, there are only two mutually exclusive and exhaustive possibilities:
- **Vertex $k$ is NOT an intermediate node of $p$:** Then all intermediate vertices of $p$ belong to $\{1, \dots, k-1\}$. Consequently, the shortest distance between $i$ and $j$ remains unchanged from the previous step and is given by $d_{ij}^{(k-1)}$.
- **Vertex $k$ IS an intermediate node of $p$:** Assuming no negative cycles exist, the simple path visits node $k$ exactly once. We can then decompose path $p$ into two subpaths: one from $i$ to $k$ and one from $k$ to $j$. By the optimal substructure of shortest paths, both subpaths must be minimal, and their intermediate nodes can only belong to $\{1, \dots, k-1\}$. Hence the total cost is $d_{ik}^{(k-1)} + d_{kj}^{(k-1)}$. Because the optimal solution must be the better of these two choices, the minimum operator ensures the correctness of the solution.
  The algorithm computes matrices for $k=1 \dots n$, in $\mathcal{O}(n^3)$ time and $\mathcal{O}(n^2)$ space.
