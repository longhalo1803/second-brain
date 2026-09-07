---
title: "9 Given a binary tree T, write a recursive function Full(t) that returns TRUE if t..."
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
  - "9 Given a binary tree T, write a recursive function Full(t) that returns TRUE if t..."
---

# 🎴 9 Given a binary tree T, write a recursive function Full(t) that returns TRUE if t...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 9 Given a binary tree $T$, write a recursive function `Full(t)` that returns `TRUE` if the tree is **full** (every node has either zero or two children), and `FALSE` otherwise. #card

?
**Base case:**
• Empty tree (`t = NIL`) or leaf (`t.left = NIL` and `t.right = NIL`): returns `TRUE`.
• Node with only one child (only one between `t.left` and `t.right` is `NIL`): returns `FALSE`.
**Recursive case:**
Node with two children: makes recursive calls on both subtrees and returns the `AND` of the results.

**Pseudocode:**

```text
Full(t)
    if t = NIL then return TRUE
    if t.left = NIL AND t.right = NIL then return TRUE
    if t.left ≠q NIL AND t.right ≠q NIL then
        return (Full(t.left) AND Full(t.right))
    else return FALSE
```
