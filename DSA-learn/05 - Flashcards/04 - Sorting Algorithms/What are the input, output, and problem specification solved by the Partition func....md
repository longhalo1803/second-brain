---
title: "What are the input, output, and problem specification solved by the Partition func..."
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
  - "What are the input, output, and problem specification solved by the Partition func..."
---

# 🎴 What are the input, output, and problem specification solved by the Partition func...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the input, output, and problem specification solved by the `Partition` function in QuickSort? #card

?
**Input:** array $A$ and two indices $p$ and $r$ such that $0 \le p \le r \le n-1$.
**Output:** index $q$ (with $p \le q \le r$) such that:

- All elements to the left of $A[q]$ are $\le A[q]$ and
- All elements to the right of $A[q]$ are $> A[q]$
