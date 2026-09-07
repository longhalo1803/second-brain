---
title: "What is the general purpose of graph traversal, and what are the main differences..."
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
  - "What is the general purpose of graph traversal, and what are the main differences..."
---

# 🎴 What is the general purpose of graph traversal, and what are the main differences...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the general purpose of graph traversal, and what are the main differences between Depth-First Search (DFS) and Breadth-First Search (BFS)? #card

?
A **graph traversal** is a strategy to analyze every node of the graph, one at a time.

CharacteristicDepth-First Search (DFS)Breadth-First Search (BFS)**Strategy**Extends _pre/post-order_ traversals on trees: after visiting a node, it tries to move as far away as possible along the current path before backtracking.Extends level-order traversal (BFS) on trees: starting from a source, it visits all direct neighbors, then the neighbors' neighbors, and so on.**Main purpose**Analyze the **entire graph**, including handling multiple connected components.Visit all nodes **reachable from a source node** and compute shortest paths (in terms of number of edges).**Data structure used\****Stack** / Recursion.**Queue** (FIFO).
