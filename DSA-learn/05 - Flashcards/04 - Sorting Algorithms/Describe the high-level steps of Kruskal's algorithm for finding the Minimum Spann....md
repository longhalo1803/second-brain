---
title: "Describe the high-level steps of Kruskal's algorithm for finding the Minimum Spann..."
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
  - "Describe the high-level steps of Kruskal's algorithm for finding the Minimum Spann..."
---

# 🎴 Describe the high-level steps of Kruskal's algorithm for finding the Minimum Spann...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Describe the high-level steps of Kruskal's algorithm for finding the Minimum Spanning Tree. #card

?
**Kruskal's Algorithm** operates by building a forest of trees that are iteratively merged:

- **Sorting:** Sort all edges $E$ of the graph in non-decreasing order with respect to their weight $c(e)$.
- **Initialization:** Initially, each node of the graph forms an isolated tree (a connected component of its own).
- **Iterative Selection:** Iterate through the sorted edges from lightest to heaviest:
- If edge $(u,v)$ connects two vertices belonging to **two distinct connected components** (that is, its addition _does not generate a cycle_), the edge is **included** in the MST and the two components are merged.
- Otherwise, the edge is **discarded**.
- **Termination:** The algorithm terminates when exactly $|V| - 1$ edges have been selected (or when all edges have been examined).
