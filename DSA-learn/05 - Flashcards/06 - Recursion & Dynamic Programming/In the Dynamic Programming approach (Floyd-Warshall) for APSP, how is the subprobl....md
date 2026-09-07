---
title: "In the Dynamic Programming approach (Floyd-Warshall) for APSP, how is the subprobl..."
tags:
  - dsa
  - flashcards
  - clrs
  - dynamic-programming
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "In the Dynamic Programming approach (Floyd-Warshall) for APSP, how is the subprobl..."
---

# 🎴 In the Dynamic Programming approach (Floyd-Warshall) for APSP, how is the subprobl...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: In the Dynamic Programming approach (Floyd-Warshall) for APSP, how is the subproblem formally defined? #card

?
To apply Dynamic Programming to the APSP problem, we define the subproblem as follows:

Given three vertices $i, j, k \in V$, with $V = \{1, 2, \dots, n\}$:
$\textsf{dist}(i, j, k)$ = length of the shortest path from node $i$ to node $j$ that uses _only_ vertices from the set $\{1, 2, \dots, k\}$ as intermediate nodes.

**Domain of variables:**

- $i, j \in \{1, 2, \dots, n\}$ (starting and ending nodes).
- $k \in \{0, 1, 2, \dots, n\}$ (set of allowed intermediate nodes).
  **Special cases:**
  If no such shortest path exists using only nodes in $\{1, \dots, k\}$, we set $\textsf{dist}(i, j, k) = +\infty$.

📌 Note: This formulation requires maintaining $n+1$ matrices of size $n \times n$. The idea of gradually expanding the set of allowed intermediate nodes from $0$ to $n$ resembles the technique used for the 0-1 knapsack problem without repetition.
