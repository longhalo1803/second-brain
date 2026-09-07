---
title: "How is the height of a binary tree T recursively calculated Show the main pseudoco..."
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
  - "How is the height of a binary tree T recursively calculated Show the main pseudoco..."
---

# 🎴 How is the height of a binary tree T recursively calculated Show the main pseudoco...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 How is the height of a binary tree `T` **recursively** calculated? Show the main pseudocode variants. #card

?
Height is the length of the longest path from the root to a leaf.

**Variant 1: Base case empty tree (empty height = -1)**

```text
Height(t)
    if t = NIL
    then return {-1}
    else return 1 + {Height(t.right), Height(t.left)}
```

**Variant 2: Base case leaf (height = 0) with wrapper**

```text
Height(t)
    if t.right = t.left = NIL then return 0
    h1 := 0, h2 := 0
    if t.left ≠q NIL then h1 := Height(t.left)
    if t.right ≠q NIL then h2 := Height(t.right)
    return 1 + {h1, h2}
```

Main wrapper function:

```text
TreeHeight(T)
    if T = NIL then return {-1}
    else return Height(T)
```

**Variant 3: Both base cases**

```text
Height(t)
    if t = NIL then return {-1}
    if t.right = t.left = NIL then return 0
    return 1 + {Height(t.right), Height(t.left)}
```
