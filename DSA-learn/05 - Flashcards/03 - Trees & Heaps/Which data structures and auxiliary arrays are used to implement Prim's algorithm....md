---
title: "Which data structures and auxiliary arrays are used to implement Prim's algorithm..."
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
  - "Which data structures and auxiliary arrays are used to implement Prim's algorithm..."
---

# 🎴 Which data structures and auxiliary arrays are used to implement Prim's algorithm...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Which data structures and auxiliary arrays are used to implement Prim's algorithm efficiently? #card

?
Prim's algorithm uses the following data structures:

- **Set / Boolean array `S[v]`:** `S[v] = 1` if node $v$ is already part of the constructed tree, `0` otherwise.
- **Array `cost[v]`:** stores the minimum weight among all edges connecting node $v$ (not yet in the tree) to a node already present in the tree. For the source node $s$, $\textsf{cost}[s] = 0$; for other nodes initially $\textsf{cost}[v] = +\infty$.
- **Array `prev[v]`:** stores the parent node of $v$ in the MST (to reconstruct the tree at the end).
- **Priority Queue (Min-Heap) `Q`:** contains all pairs $(v, \textsf{cost}[v])$ of unprocessed nodes. Allows extracting the node outside the tree with the minimum `cost` value in logarithmic time.
