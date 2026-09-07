---
title: "Provide the recursive pseudocode to count the number of nodes of a binary tree T (..."
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
  - "Provide the recursive pseudocode to count the number of nodes of a binary tree T (..."
---

# 🎴 Provide the recursive pseudocode to count the number of nodes of a binary tree T (...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝🟢 Provide the recursive pseudocode to count the number of nodes of a binary tree `T` (base case: empty tree). #card

?
**Algorithm logic:**

- **Base case:** empty tree (`t = NIL`) $\to$ returns 0.
- **Recursive case:** non-empty tree $\to$ returns 1 (the root) plus the sum of the number of nodes in the left subtree and in the right subtree.
  **Pseudocode:**

```text
countNodes(t)
    if t = NIL then return 0
    else return 1 + countNodes(t.left) + countNodes(t.right)
```

Main call: $\textsf{countNodes(T)}$
