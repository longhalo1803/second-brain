---
title: "Which supporting data structures and strategies are needed to implement recursive..."
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
  - "Which supporting data structures and strategies are needed to implement recursive..."
---

# 🎴 Which supporting data structures and strategies are needed to implement recursive...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Which supporting data structures and strategies are needed to implement recursive DFS on a graph? #card

?
You need to:
• Use **recursion **→ after visiting a node, we recursively visit its unvisited neighbors
• Have a way to **know if a node has already been visited** → boolean array `visited[1..n]`

Therefore, to implement recursive DFS, the following components are needed:

- **Tracking array `visited[1..n]`:** Boolean array to avoid visiting the same node multiple times and prevent infinite loops.
- `visited[v] = FALSE`: node not yet encountered during the traversal.
- `visited[v] = TRUE`: node already encountered/visited.
- **Call Stack:** Recursion implicitly manages the active call stack, allowing backtracking when a node has no more unvisited neighbors.
- **Node examination points:**
- **Pre-visit case:** Executed as soon as the node is entered (before recursive calls on neighbors).
- **Post-visit case:** Executed when the traversal of all descendants of the node is completed (after recursive calls have returned).
