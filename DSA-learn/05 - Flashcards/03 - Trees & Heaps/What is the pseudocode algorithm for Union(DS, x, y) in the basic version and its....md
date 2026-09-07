---
title: "What is the pseudocode algorithm for Union(DS, x, y) in the basic version and its..."
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
  - "What is the pseudocode algorithm for Union(DS, x, y) in the basic version and its..."
---

# 🎴 What is the pseudocode algorithm for Union(DS, x, y) in the basic version and its...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the pseudocode algorithm for `Union(DS, x, y)` in the basic version and its complexity? #card

?
The `Union` operation determines the roots of both sets using `Find-set` and, if distinct, links the root of the first tree under the root of the second:

```text
Union(DS, x, y)
    xr := Find-set(DS, x)                // {#D9534F}{≤ftarrow root of the set containing x}
    yr := Find-set(DS, y)                // {#D9534F}{≤ftarrow root of the set containing y}
    if xr ≠q yr then
        DS[xr] := yr                         // {#D9534F}{≤ftarrow link root xr under root yr}
```

**Computational cost**:
Dominated by the two search operations, i.e., $O(h_x + h_y)$, where $h_x$ and $h_y$ are the heights of the trees containing $x$ and $y$. In the worst case without heuristics, it is $O(n)$.
