---
title: "How is the full shortest path between two nodes i and j reconstructed using the pr..."
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
  - "How is the full shortest path between two nodes i and j reconstructed using the pr..."
---

# 🎴 How is the full shortest path between two nodes i and j reconstructed using the pr...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is the full shortest path between two nodes $i$ and $j$ reconstructed using the predecessor matrix $P$, and what is its cost? #card

?
The sequence of vertices is reconstructed by tracing **backwards** from the destination $j$ towards the origin $i$ (a _backtracking_ procedure):

- $p_1 = P[i, j]$ (node immediately preceding $j$)
- $p_2 = P[i, p_1]$ (node preceding $p_1$)
- $p_3 = P[i, p_2]$
- ...
- $p_t = P[i, p_{t-1}]$, until $i = P[i, p_t]$ is reached.
  Reversing the order of the found predecessors yields the shortest path from $i$ to $j$ as the ordered sequence of nodes:

$$

i, \, p*t, \, p*{t-1}, \, \dots, \, p_3, \, p_2, \, p_1, \, j

$$

**Computational cost:**
Since a simple path contains at most $n - 1$ edges, the backtracking takes at most $O(n)$ steps. The cost to retrieve and print a single shortest path is therefore $O(n)$.
