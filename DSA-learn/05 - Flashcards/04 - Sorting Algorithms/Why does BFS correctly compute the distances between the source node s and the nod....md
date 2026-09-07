---
title: "Why does BFS correctly compute the distances between the source node s and the nod..."
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Why does BFS correctly compute the distances between the source node s and the nod..."
---

# 🎴 Why does BFS correctly compute the distances between the source node s and the nod...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: \*Why does BFS correctly compute the distances between the source node $s$ and the nodes reachable from $s$?

On which partition of the nodes (Three-set invariant) is the proof of correctness of BFS based? #card
?
At the beginning of EVERY iteration of BFS, for an integer $d < n$, the graph nodes are partitioned into three disjoint sets:

- **STATIC WORLD**: nodes already extracted from the queue, whose neighbors have been completely explored.
  • For them, $\text{dist}[u] \le d$ is the **correct** shortest path value.

- **FRONTIER**: nodes already discovered whose adjacencies have NOT yet been examined.
  • Represents the contents of the FIFO queue $Q$.
  • Their values satisfy $d \le \text{dist}[u] \le d+1$ and are correct.

- **DISTANT WORLD**: nodes not yet discovered.
  • For them, $\text{dist}[u] = +\infty$.
