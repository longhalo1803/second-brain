---
title: "What is the Floyd-Warshall recurrence relation to compute text{dist}(i, j, k) from..."
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
  - "What is the Floyd-Warshall recurrence relation to compute text{dist}(i, j, k) from..."
---

# 🎴 What is the Floyd-Warshall recurrence relation to compute text{dist}(i, j, k) from...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: What is the Floyd-Warshall recurrence relation to compute $\text{dist}(i, j, k)$ from the smaller subproblems at level $k-1$? #card

?
The recurrence is based on deciding whether the shortest path between $i$ and $j$ with intermediate nodes in $\{1, 2, \dots, k\}$ **passes through node $k$ or does not pass through it**:

```text
dist(i, j, k) = {cases} dist(i, j, k-1)
dist(i, k, k-1) + dist(k, j, k-1) {cases}
```

**Explanation of the two options:**

- **The path does NOT pass through $k$:** all intermediate nodes belong to $\{1, \dots, k-1\}$. Consequently, the optimal length is $\textsf{dist}(i, j, k-1)$.
- **The path PASSES through $k$:** node $k$ is visited only once (simple path). The route splits into two subpaths: one from $i$ to $k$ and one from $k$ to $j$, both having intermediate nodes belonging solely to $\{1, \dots, k-1\}$. The total length is given by $\textsf{dist}(i, k, k-1) + \textsf{dist}(k, j, k-1)$.
