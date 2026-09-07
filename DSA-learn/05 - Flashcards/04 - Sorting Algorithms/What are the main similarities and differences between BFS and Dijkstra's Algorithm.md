---
title: "What are the main similarities and differences between BFS and Dijkstra's Algorithm"
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
  - "What are the main similarities and differences between BFS and Dijkstra's Algorithm"
---

# 🎴 What are the main similarities and differences between BFS and Dijkstra's Algorithm

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the main similarities and differences between BFS and Dijkstra's Algorithm? #card

?
**Similarities with BFS:**

- Both use an array $\textsf{dist}[1..n]$ to store the distances of nodes from the source $s$;
- Nodes are partitioned into _discovered_ ($\textsf{dist}[u] \neq +\infty$) and _not yet discovered_ ($\textsf{dist}[u] = +\infty$);
- At each iteration, a node is selected from among the discovered ones and its neighbors are explored.
  **Differences from BFS:**

- **Non-final distances:** in BFS, a node's distance is computed only once as soon as it is discovered. In Dijkstra, discovered nodes have provisional distances that can be reduced later.
- **Selection criterion:** at each step, Dijkstra chooses the discovered but not yet _visited_ node with the **minimum** $\textsf{dist}[\cdot]$ value.
- **Update (_**relaxation**_):** the distance $\textsf{dist}[u]$ is updated whenever a shorter path to $u$ is found.📌 Remember: a node is visited
  when we have
  explored all of its neighbors.
