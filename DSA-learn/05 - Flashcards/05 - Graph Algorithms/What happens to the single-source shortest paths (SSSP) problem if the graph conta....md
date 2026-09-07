---
title: "What happens to the single-source shortest paths (SSSP) problem if the graph conta..."
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
  - "What happens to the single-source shortest paths (SSSP) problem if the graph conta..."
---

# 🎴 What happens to the single-source shortest paths (SSSP) problem if the graph conta...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What happens to the single-source shortest paths (SSSP) problem if the graph contains negative weights and a negative cycle? #card

?
If the graph contains a **cycle of negative total length (or weight)** reachable from the source $s$, the shortest path problem is **ill-posed**.

By traversing a negative cycle an arbitrary number of times, the length of the path keeps decreasing indefinitely, tending towards $-\infty$. Consequently, there is no well-defined shortest distance for the nodes reachable from such a cycle.

📝 Example:
If from $s$ one reaches a node $u$ that is part of a cycle with total cost $L_3 < 0$, the distance of $u$ from $s$ can be made arbitrarily small by repeatedly traversing cycle $L_3$.
