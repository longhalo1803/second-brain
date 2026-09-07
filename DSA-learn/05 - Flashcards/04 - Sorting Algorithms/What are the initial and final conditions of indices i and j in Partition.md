---
title: "What are the initial and final conditions of indices i and j in Partition"
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What are the initial and final conditions of indices i and j in Partition"
---

# 🎴 What are the initial and final conditions of indices i and j in Partition

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the initial and final conditions of indices $i$ and $j$ in `Partition`? #card

?

- **Before the first iteration:** the array has not been examined yet, so the $\le x$ and $> x$ regions are empty. The indices are set to:

```text
i = p - 1 and j = p
```

- **At the last iteration:** index $j$ has reached the last element before the pivot:

$$
j = r - 1
$$

All elements in $A[p..r-1]$ have been partitioned into the two regions $\le x$ and $> x$. It only remains to swap the pivot in $A[r]$ with $A[i+1]$.
