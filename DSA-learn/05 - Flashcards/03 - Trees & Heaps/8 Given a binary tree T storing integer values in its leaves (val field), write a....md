---
title: "8 Given a binary tree T storing integer values in its leaves (val field), write a..."
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
  - "8 Given a binary tree T storing integer values in its leaves (val field), write a..."
---

# 🎴 8 Given a binary tree T storing integer values in its leaves (val field), write a...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 8 Given a binary tree $T$ storing integer values in its leaves (`val` field), write a recursive function `SumLeaves(t)` that returns the sum of all values stored in the leaves of the tree. #card

?
**Base case:
**• If the tree is empty (`t = NIL`): returns $0$.
• If the node is a leaf (`t.left = NIL` and `t.right = NIL`): returns `t.val`.
**Recursive case:
**If the node is internal: returns the sum of the values obtained recursively on the left and right subtrees.

**Pseudocode:**

```text
SumLeaves(t)
    if t = NIL then return 0
    if t.left = NIL AND t.right = NIL then
        return t.val
    else
        return SumLeaves(t.left) + SumLeaves(t.right)
```
