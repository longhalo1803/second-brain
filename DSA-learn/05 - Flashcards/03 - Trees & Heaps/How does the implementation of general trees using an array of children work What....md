---
title: "How does the implementation of general trees using an array of children work What..."
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
  - "How does the implementation of general trees using an array of children work What..."
---

# 🎴 How does the implementation of general trees using an array of children work What...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How does the implementation of general trees using an _**array of children**_ work? What are its advantages and disadvantages? #card

?
It assumes that the maximum degree (max number of children) of the tree is a known value $k$. Each node contains a fixed array of $k$ child pointers.

**Node fields (`tree_node`):**

- Fields $C_1, C_2, \dots, C_k$: pointers to the 1st, 2nd, ..., $k$-th child.
- `parent`: (optional) pointer to the parent.
- `val`: stored value.
  **Advantages and Disadvantages:**

- **Advantage:** direct access to the $i$-th child in $O(1)$ time.
- **Disadvantage (possible **wasted memory**):** if many nodes have fewer than $k$ children, many unused pointers set to `NIL` are allocated.
