---
title: "Provide the recursive pseudocode to count the number of nodes of a binary tree T (... (2)"
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
  - "Provide the recursive pseudocode to count the number of nodes of a binary tree T (... (2)"
---

# 🎴 Provide the recursive pseudocode to count the number of nodes of a binary tree T (... (2)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Provide the recursive pseudocode to count the number of nodes of a binary tree `T` (base case: leaf). #card

?
**Algorithm logic:**

- **Base case:** tree consisting of a single leaf (`t.left = t.right = NIL`) $\to$ returns 1.
- **Recursive case:** sum 1 (the root) and the number of nodes in the left and right subtrees, after first checking their existence (i.e., that they are `NOT= NIL`).
  **Pseudocode:**

```text
countNodes(t)
        if t.right = t.left = NIL // leaf node if both pointers are null
    then return 1
    else
        n_l := 0, n_r := 0
        if t.left ≠q NIL then n_l := countNodes(t.left)
        if t.right ≠q NIL then n_r := countNodes(t.right)
        return 1 + n_l + n_r
```

⚠️ Warning: this version assumes that the initial input pointer `T` is not `NIL`.
📌 Note: it is simpler as a base case to check if the current node `t` is `NIL`, rather than checking its children as done here.
