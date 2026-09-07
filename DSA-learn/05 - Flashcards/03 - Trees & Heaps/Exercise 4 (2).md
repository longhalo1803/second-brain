---
title: "Exercise 4 (2)"
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
  - "Exercise 4 (2)"
---

# 🎴 Exercise 4 (2)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Exercise 4

Show an example of a graph in which there exists a minimum spanning tree that coincides with a shortest-path tree (choose which node is the source).
Then modify the graph by changing edge weights and/or adding edges so that this is no longer true. #card
?
There are at least two fairly simple ways:

- draw a graph with edges all having the same weight and compute the shortest-path tree with Dijkstra. The exact same edges of the shortest-path tree form an MST.
- draw a tree with edges of any arbitrary weight k (as long as it is the same for all of them), add edges randomly with weight greater than $n\cdot k$. The edges of weight k form both the shortest-path tree and the unique MST.
  Naturally, more complicated examples can also be found.

Example with edges of all equal weights:

- **All edges with equal weights (e.g., 1):** The edges of the shortest-path tree (SPT) starting from 1 use edges (1,2) and (1,3) for a distance of 1 per node. These same two edges also form a valid MST (total weight 2).

Examples with different weights:

- **Left graph (MST = SPT):**

- **MST:** To connect the 3 nodes with the minimum cost, the tree chooses edges (1,2) and (1,3) for a total weight of $2 + 2 = 4$.

- **SPT (from node 1):** The shortest path from 1 to 2 has cost 2 (edge 1-2). The shortest path from 1 to 3 has cost 2 (edge 1-3). The shortest-path tree coincides exactly with the MST `{(1,2), (1,3)}`.

- **Right graph (MST ≠ SPT):**

- **MST:** To minimize the total cost, it uses edge (2,3) of weight 1 and a choice between (1,2) and (1,3) of weight 2 (total cost = 3).

- **SPT (from node 1):** To reach 2 and 3 from source 1 in the shortest way possible, edges (1,2) and (1,3) are still needed (total cost = 4). The two trees no longer coincide.
