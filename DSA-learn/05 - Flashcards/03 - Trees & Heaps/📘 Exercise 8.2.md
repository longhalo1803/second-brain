---
title: "📘 Exercise 8.2"
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
  - "📘 Exercise 8.2"
---

# 🎴 📘 Exercise 8.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 8.2

Assume a procedure `delete_node(p)` is available that deallocates node $p$ from memory.

**Input:** A binary tree $T$ implemented with nodes and pointers (fields: key, left child pointer, right child pointer).
**Output:** Deallocate all nodes of the tree.

Provide the pseudocode of a recursive procedure for the problem. State the base case and the recursive case in words, and analyze the computational complexity. #card
?
**Reasoning:**
A node cannot be deallocated before its children have been processed, otherwise the pointers to its subtrees would become dangling. Hence, a post-order traversal (left, right, root) is mandatory.

**Base Case and Recursive Case:**

- _Base Case:_ If pointer $p = \text{NIL}$, there is nothing to delete; return immediately.
- _Recursive Case:_ If $p \ne \text{NIL}$, recursively call the deletion on $p.left$, recursively call on $p.right$, and finally invoke `delete_node(p)`.
  **Pseudocode:**

```text
Procedure DeleteTree(p):
    if p ≠ NIL then
        DeleteTree(p.left)
        DeleteTree(p.right)
        delete_node(p)
```

**Complexity:**

- Time Complexity: $\Theta(n)$, where $n$ is the number of nodes in $T$, as each node is visited and deallocated exactly once.
- Space Complexity: $O(h)$ stack frames, where $h$ is tree height.
