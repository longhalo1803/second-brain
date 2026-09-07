---
title: "Is the spanning tree obtained with DFS on a connected graph unique Justify the ans..."
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
  - "Is the spanning tree obtained with DFS on a connected graph unique Justify the ans..."
---

# 🎴 Is the spanning tree obtained with DFS on a connected graph unique Justify the ans...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Is the spanning tree obtained with DFS on a connected graph unique? Justify the answer. #card

?
No, the spanning tree is NOT unique.

The structure of the spanning tree obtained via DFS depends on two key factors:

- **The source node (root):** Starting the traversal from a different node yields a spanning tree with a different ancestor/parent structure.
- **The adjacency order of the nodes:** The order in which the incident edges of a node are examined (for example the order in the adjacency lists) determines which neighbor is visited first.📝 Example:
  In a triangular cycle graph on nodes $\{1, 2, 3\}$:
  • starting from $1$ and visiting $2$ first yields the tree with edges $(1,2)$ and $(2,3)$.
  • starting from $2$ and visiting $3$ first yields the tree with edges $(2,3)$ and $(3,1)$.
