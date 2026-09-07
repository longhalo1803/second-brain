---
title: "📘 Exercise 26.1"
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
  - "📘 Exercise 26.1"
---

# 🎴 📘 Exercise 26.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 26.1

**Input:** A generic binary tree $T$ implemented with nodes and pointers (fields $val, left, right$).
**Output:**

- _Variant 1:_ The maximum absolute difference between the depths of two leaves in $T$ (if $T$ has only one leaf, return 0).
- _Variant 2:_ The number of pairs of leaves in $T$ that have the maximum difference in depth (if $T$ has only one leaf, return 0).Show an example, describe an algorithm, provide pseudocode, and analyze computational complexity. #card
  ?
  **Reasoning:**
  The maximum depth difference between two leaves is simply $max\_depth - min\_depth$ among all leaves. For Variant 2, the number of pairs attaining this difference is $count(min\_depth) \times count(max\_depth)$ (or $\binom{k}{2}$ if $min\_depth = max\_depth$). A single tree traversal finds these values.

**Pseudocode:**

```text
Algorithm LeafDepthAnalysis(T):
    if T = NIL then return 0
    min_d ≤ftarrow ∈fty, \; max_d ≤ftarrow -∈fty
    c_{min} ≤ftarrow 0, \; c_{max} ≤ftarrow 0
    Traverse(T, 0, min_d, max_d, c_{min}, c_{max})
    if min_d = max_d then
        // Variant 1 returns 0; Variant 2 returns pairs among leaves of same depth
        return (0, \; c_{min} (c_{min} - 1) / 2)
    return (max_d - min_d, \; c_{min} c_{max})

Procedure Traverse(u, d, ref min_d, max_d, c_{min}, c_{max}):
    if u.left = NIL u.right = NIL then
        if d  max_d then max_d ≤ftarrow d; \; c_{max} ≤ftarrow 1
        else if d = max_d then c_{max} ≤ftarrow c_{max} + 1
        return
    if u.left ≠ NIL then Traverse(u.left, d + 1, min_d, max_d, c_{min}, c_{max})
    if u.right ≠ NIL then Traverse(u.right, d + 1, min_d, max_d, c_{min}, c_{max})
```

**Complexity:**
$\Theta(n)$ time and $O(h)$ auxiliary stack space.
