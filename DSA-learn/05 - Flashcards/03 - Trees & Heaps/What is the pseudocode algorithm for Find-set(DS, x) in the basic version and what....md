---
title: "What is the pseudocode algorithm for Find-set(DS, x) in the basic version and what..."
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
  - "What is the pseudocode algorithm for Find-set(DS, x) in the basic version and what..."
---

# 🎴 What is the pseudocode algorithm for Find-set(DS, x) in the basic version and what...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the pseudocode algorithm for `Find-set(DS, x)` in the basic version and what does its complexity depend on? #card

?
The `Find-set` operation recursively ascends the parent path in the array `DS` until it reaches the root of the tree:

```text
Find-set(DS, x)
    if DS[x] = x then
        return x                             // {#D9534F}{≤ftarrow if x is the root, return x}
    else
        return Find-set(DS, DS[x])           // {#D9534F}{≤ftarrow recursively ascend to the parent}
```

**Computational cost**:
$O(h)$, proportional to the height $h$ of the tree containing node $x$. In the worst case, the height can be linear, making the complexity $O(n)$.
