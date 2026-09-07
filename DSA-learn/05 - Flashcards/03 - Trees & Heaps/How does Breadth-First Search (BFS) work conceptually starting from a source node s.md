---
title: "How does Breadth-First Search (BFS) work conceptually starting from a source node s"
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
  - "How does Breadth-First Search (BFS) work conceptually starting from a source node s"
---

# 🎴 How does Breadth-First Search (BFS) work conceptually starting from a source node s

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How does Breadth-First Search (BFS) work conceptually starting from a source node $s$?

📝 Show an example for undirected and directed graphs and the corresponding BFS spanning tree. #card
?
Breadth-First Search (BFS) explores the graph "in concentric waves" or by **levels of increasing distance** from the source $s$:

- **Level 0**: Start from the source node $s$ (distance 0).
- **Level 1**: Visit all **direct neighbors** of $s$ (distance 1).
- **Level 2**: Visit the unvisited neighbors of level 1 nodes (distance 2).
- **Level $k$**: Visit the unvisited neighbors of level $k-1$ nodes (distance $k$).The edges traversed during the initial discoveries of nodes form a **spanning tree** (BFS tree) rooted at $s$.

📝 Example:
If the source is node 3, BFS explores first the neighbors of source 3, {4, 5}, then the neighbors of neighbors of source 3 (not yet visited), {6, 7, 8, 9}, and so on.

📌 Note:
In a directed graph, edges can only be traversed in the direction of the arrow. Consequently:
• **Only** nodes for which there exists a directed path from the source $s$ are visited.
• Nodes with no directed path from $s$ remain with distance **$\text{dist}[u] = +\infty$** and never enter the BFS queue.
