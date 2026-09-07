---
title: "How is the final solution of the APSP problem obtained and how do the matrices cha..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "How is the final solution of the APSP problem obtained and how do the matrices cha..."
---

# 🎴 How is the final solution of the APSP problem obtained and how do the matrices cha...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: How is the final solution of the APSP problem obtained and how do the matrices change during computation? #card

?
After recursively computing the matrices for all levels $k = 1, 2, \dots, n$, the final matrix $\textsf{dist}(i, j, n)$ (which represents the **optimal solution**) contains the absolute shortest path length between every pair of nodes $(i, j)$.

There is a dependency between the matrices: to compute the matrix for level $k$ (i.e., $D^{(k)}$), **only** the matrix for the previous level $k-1$ (i.e., $D^{(k-1)}$) is needed.

📌 Note:
This property allows optimizing memory space by keeping only one (or two) matrices of size $n \times n$ active at a time, rather than storing all $n+1$ matrices.
