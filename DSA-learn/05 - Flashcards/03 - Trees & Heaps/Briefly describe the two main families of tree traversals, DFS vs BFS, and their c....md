---
title: "Briefly describe the two main families of tree traversals, DFS vs BFS, and their c..."
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
  - "Briefly describe the two main families of tree traversals, DFS vs BFS, and their c..."
---

# 🎴 Briefly describe the two main families of tree traversals, DFS vs BFS, and their c...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Briefly describe the two main families of tree traversals, DFS vs BFS, and their computational cost. #card

?
Strategies to visit all nodes of a tree are divided into:

- **Depth First Search (DFS):**
  Explores the tree by going down along branches before backtracking. Recursively visits subtrees using recursion (i.e., a _stack_). Variants: _pre-order_, _in-order_, _post-order_.
- **Breadth First Search (BFS):**
  Explores the tree one level at a time, starting from the root. Explicitly uses a **queue** (FIFO).
  **Computational cost:**
  For both families of traversals, the time complexity is:

$$

O(n \cdot f(n))

$$

where $n$ is the number of nodes in the tree and $O(f(n))$ is the cost of processing a single node.
If processing a single node takes constant time $O(1)$, the traversal takes $\Theta(n)$ time.
