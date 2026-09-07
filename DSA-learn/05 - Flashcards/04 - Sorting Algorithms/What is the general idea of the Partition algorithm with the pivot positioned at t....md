---
title: "What is the general idea of the Partition algorithm with the pivot positioned at t..."
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
  - "What is the general idea of the Partition algorithm with the pivot positioned at t..."
---

# 🎴 What is the general idea of the Partition algorithm with the pivot positioned at t...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the general idea of the `Partition` algorithm with the pivot positioned at the end? #card

?
The algorithm selects the last element of the sub-array as the pivot $x = A[r]$ and rearranges the portion $A[p..r]$ in 3 phases:

- Chooses $t = r$ ($x = A[r]$).
- Compares $x$ with all elements in $A[p..r-1]$, moving elements $\le x$ to the left and elements $> x$ to the right.
- Finally places the pivot into its final position $q$ between the region $\le x$ and the region $> x$.
