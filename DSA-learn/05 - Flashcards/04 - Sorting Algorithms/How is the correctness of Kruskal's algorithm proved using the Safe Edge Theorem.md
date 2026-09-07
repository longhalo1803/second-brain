---
title: "How is the correctness of Kruskal's algorithm proved using the Safe Edge Theorem"
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
  - "How is the correctness of Kruskal's algorithm proved using the Safe Edge Theorem"
---

# 🎴 How is the correctness of Kruskal's algorithm proved using the Safe Edge Theorem

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How is the correctness of Kruskal's algorithm proved using the Safe Edge Theorem? #card

?
The proof of Kruskal's correctness relies on showing that **at each iteration, the algorithm chooses a safe edge**:

- Let $(u,v)$ be the edge chosen by Kruskal at the $i$-th iteration.
- The algorithm selects $(u,v)$ because it is the minimum-cost edge in the sorted order that does not form cycles with previously inserted edges.
- Since it creates no cycles, $u$ and $v$ belong to two distinct connected components of the current forest.
- We define the cut $(S, V \setminus S)$ by setting $S$ as the set of vertices in the connected component containing $u$.
- Edge $(u,v)$ crosses this cut. Furthermore, since edges are examined in non-decreasing order of cost, $(u,v)$ is the **minimum-cost** edge in the entire graph among those available that cross the cut $(S, V \setminus S)$.
- By the **Safe Edge Theorem**, $(u,v)$ is a safe edge and is part of an MST.By induction on all $|V|-1$ chosen edges, the final set of edges constitutes an MST. $\blacksquare$
