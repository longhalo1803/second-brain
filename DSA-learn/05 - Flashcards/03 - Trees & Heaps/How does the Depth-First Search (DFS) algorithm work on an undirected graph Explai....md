---
title: "How does the Depth-First Search (DFS) algorithm work on an undirected graph Explai..."
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
  - "How does the Depth-First Search (DFS) algorithm work on an undirected graph Explai..."
---

# 🎴 How does the Depth-First Search (DFS) algorithm work on an undirected graph Explai...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ⭐ How does the Depth-First Search (DFS) algorithm work on an undirected graph? Explain the exploration and backtracking mechanism. #card

?
**DFS (Depth First Search)** explores a graph by moving as deeply as possible before backtracking.

**Operating mechanism:**

- Start from a source node (or any unvisited node) and mark it as **visited**.
- Choose an adjacent node that has not yet been visited and move to it, continuing recursively in depth.
- When reaching a node with no unexplored neighbors (a "dead end" or a node whose neighbors have all already been visited), perform **backtracking**: retrace steps back along the incoming path until reaching a node that still has unexplored neighbors.
- The traversal terminates when having returned to the starting point and there are no other edges/nodes to explore in the connected component. If there are unexplored nodes in other components, restart from one of them.📌 Note: DFS guarantees that every node and edge of the graph is visited once in linear time.

  visited node

  edge leading to an unvisited node

  edge leading to an already visited node

📌 Note 2: the choice order of the next node among neighbors in the animated example above is just an example (a rule could be "always visit the neighbor with the lowest index", or "follow the insertion order in the list" for example). The order could also be different, but the principle of DFS remains the same.
