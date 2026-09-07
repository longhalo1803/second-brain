---
title: "📘 Exercise 19.1"
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
  - "📘 Exercise 19.1"
---

# 🎴 📘 Exercise 19.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 19.1

Given a binary tree $T$ where each node is colored either black or white:

- Count the total number of white nodes in $T$ in $O(n)$ time.
- Find the maximum size (number of nodes) of a monochromatic subtree in $T$ in $O(n)$ time (a monochromatic subtree has all its nodes of the same color).Describe the algorithms in words, provide pseudocode, and state computational complexity. #card
  ?
  **Reasoning:**
  Both problems are solved via post-order tree traversals. Counting white nodes simply sums the counts from subtrees plus 1 if the current node is white. For monochromatic subtrees, a node roots a monochromatic subtree if both child subtrees are monochromatic and have the same color as the node.

**Pseudocode:**

```text
Function CountWhite(u):
    if u = NIL then return 0
    return \; (u.color = WHITE \,?\, 1 : 0) + CountWhite(u.left) + CountWhite(u.right)

Function MaxMonoSubtree(u):
    if u = NIL then return (true, NONE, 0, 0)
    (ok_L, c_L, sz_L, max_L) ≤ftarrow MaxMonoSubtree(u.left)
    (ok_R, c_R, sz_R, max_R) ≤ftarrow MaxMonoSubtree(u.right)
    is_mono ≤ftarrow true
    if u.left ≠ NIL (not ok_L c_L ≠ u.color) then is_mono ≤ftarrow false
    if u.right ≠ NIL (not ok_R c_R ≠ u.color) then is_mono ≤ftarrow false
    curr_size ≤ftarrow 1 + (u.left ≠ NIL \,?\, sz_L : 0) + (u.right ≠ NIL \,?\, sz_R : 0)
    best ≤ftarrow (max_L, max_R)
    if is_mono then best ≤ftarrow (best, curr_size)
    return (is_mono, u.color, curr_size, best)
```

**Complexity:**
Both algorithms visit every node once: $\Theta(n)$ time, $O(h)$ auxiliary stack space.
