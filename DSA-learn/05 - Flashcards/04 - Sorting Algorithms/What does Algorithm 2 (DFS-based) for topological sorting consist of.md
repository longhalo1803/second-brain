---
title: "What does Algorithm 2 (DFS-based) for topological sorting consist of"
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
  - "What does Algorithm 2 (DFS-based) for topological sorting consist of"
---

# 🎴 What does Algorithm 2 (DFS-based) for topological sorting consist of

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What does Algorithm 2 (DFS-based) for topological sorting consist of? #card

?
Algorithm 2 computes the topological ordering by means of a **depth-first search (DFS)** of the graph.

Nodes are inserted into the topological ordering in **reverse order of their `post[]` value** (from the largest `post[]` value on the left to the smallest on the right).

**Implementation:**
When the visit of node $u$ finishes (i.e., at the end of the recursive DFS call on $u$), $u$ is pushed onto the top of a **stack** or prepended to a linked list.
At the end of the DFS, the elements popped from the stack (following LIFO order) will provide the correct topological ordering.

📌 Note:
The topological ordering corresponds to the reverse of the DFS visit completion order (post-order): it is obtained by pushing each node onto a stack at the exact moment its recursive call ends.
