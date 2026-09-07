---
title: "📘 Exercise 23.1"
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
  - "📘 Exercise 23.1"
---

# 🎴 📘 Exercise 23.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 23.1

**Input:** A binary tree $T$ implemented with nodes and pointers.
**Output:** The number of nodes in $T$ that have exactly one child.

- Describe a recursive algorithm specifying base case and recursive case, and provide pseudocode.
- Analyze the computational complexity.
- Provide an example tree of height at least 3, listing the order of recursive calls and their returned values. #card
  ?
  **Reasoning:**
  Traverse the tree recursively. For each node, evaluate whether it has exactly one child ($left \ne \text{NIL} \land right = \text{NIL}$ or vice versa), add 1 if true, and sum with recursive calls on the children.

**Algorithm & Pseudocode:**

```text
Algorithm CountSingleChildNodes(u):
    if u = NIL then return 0
    is_single ≤ftarrow (u.left ≠ NIL u.right = NIL) (u.left = NIL u.right ≠ NIL)
    current ≤ftarrow (is_single \,?\, 1 : 0)
    return current + CountSingleChildNodes(u.left) + CountSingleChildNodes(u.right)
```

**Complexity:**
$\Theta(n)$ time, visiting every node once, and $O(h)$ auxiliary recursion stack space.
