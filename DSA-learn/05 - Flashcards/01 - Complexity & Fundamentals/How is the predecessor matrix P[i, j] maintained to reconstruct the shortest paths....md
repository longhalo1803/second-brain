---
title: "How is the predecessor matrix P[i, j] maintained to reconstruct the shortest paths..."
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
  - "How is the predecessor matrix P[i, j] maintained to reconstruct the shortest paths..."
---

# 🎴 How is the predecessor matrix P[i, j] maintained to reconstruct the shortest paths...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: How is the predecessor matrix $P[i, j]$ maintained to reconstruct the shortest paths in Floyd-Warshall? #card

?
To trace the exact sequence of nodes of each shortest path, the **immediate predecessor of $j$** along the shortest path from $i$ to $j$ is stored in a matrix $P[i, j]$.

**1. Initialization ($k = 0$):**

$$
P[i, j] = \begin{cases} i & \text{if } (i, j) \in E \land i \neq j \\ 0 & \text{otherwise (no predecessor)} \end{cases}
$$

**2. Update during the loop over $k$:**
If a strictly shorter path is found passing through intermediate vertex $k$:

```text
if dist[i, j, k-1] > dist[i, k, k-1] + dist[k, j, k-1] then
    P[i, j] := P[k, j]
```

📌 Note: the predecessor of $j$ on the new optimal path from $i$ to $j$ matches the last node that precedes $j$ on the subpath from $k$ to $j$, namely $P[k, j]$.
