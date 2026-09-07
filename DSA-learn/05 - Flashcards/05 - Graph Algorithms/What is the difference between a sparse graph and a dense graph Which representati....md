---
title: "What is the difference between a sparse graph and a dense graph Which representati..."
tags:
  - dsa
  - flashcards
  - clrs
  - graphs
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the difference between a sparse graph and a dense graph Which representati..."
---

# 🎴 What is the difference between a sparse graph and a dense graph Which representati...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the difference between a sparse graph and a dense graph? Which representation is chosen in each case? #card

?
The density of a graph is given by the ratio between the number of actual edges $m$ and the theoretical maximum number $\Theta(n^2)$\*:

**Sparse graph:** has few edges, typically $m \in O(n)$.
→ It is best represented using **adjacency lists** to optimize memory space.

**Dense graph:** has many edges, i.e., $m \in \Omega(n^2)$ (close to the maximum limit).
→ It is best represented using an **adjacency matrix** to ensure fast access to edges.

\*(more precisely, with $n$ nodes the maximum number of edges is $n(n-1)$, or half of that if undirected)
