---
title: "Describe the idea and steps of Prim's algorithm for finding an MST."
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
  - "Describe the idea and steps of Prim's algorithm for finding an MST."
---

# 🎴 Describe the idea and steps of Prim's algorithm for finding an MST.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Describe the idea and steps of Prim's algorithm for finding an MST. #card

?
**Prim's Algorithm** constructs the MST by growing a single tree starting from a source node:

- **Initialization:** An arbitrary source node $s \in V$ is chosen as the root of the tree. The initial tree contains only $s$.
- **Incremental Growth:** At each iteration, among all edges connecting a node _already in the tree_ to a node _not yet in the tree_, the edge of **minimum weight** is selected.
- **Inclusion:** The destination node and the connecting edge are added to the tree.
- **Termination:** The algorithm terminates when all vertices of the graph have been included in the tree.

https://algorithms-visual.com/prim/ (click load to load pre-made graphs)
