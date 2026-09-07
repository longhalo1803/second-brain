---
title: "What are the main characteristics and differences between DFS (Depth First Search)..."
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
  - "What are the main characteristics and differences between DFS (Depth First Search)..."
---

# 🎴 What are the main characteristics and differences between DFS (Depth First Search)...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the main characteristics and differences between DFS (Depth First Search) and BFS (Breadth First Search) on graphs? For what goal is BFS used in brief? #card

?
The two main strategies for examining the nodes of a graph without duplicates differ in approach and purpose:

      Characteristic
      DFS (Depth First Search)
      BFS (Breadth First Search)


      **Strategy**
      Extension of pre/post-order traversals on trees. After a node, it tries to move as *far away* as possible along a path.
      Extension of level-order traversal on trees. Visits the source's neighbors first, then neighbors of neighbors, and so on.


      **Data Structure**
      Stack / Recursion
      FIFO Queue


      **Goal / Use**
      Visit **all** nodes in the graph (even across multiple connected components). Used for topological sorting, strongly connected components, etc.
      Visit all nodes **reachable** from a source $s$ and compute **shortest paths** (in number of edges).

📌 Note: both traversals examine each reachable node only once.
