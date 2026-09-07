---
title: "What is the structure of the array at a generic iteration j of Partition"
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
  - "What is the structure of the array at a generic iteration j of Partition"
---

# 🎴 What is the structure of the array at a generic iteration j of Partition

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the structure of the array at a generic iteration $j$ of `Partition`? #card

?
At a generic iteration of index $j$, the array is partitioned into the following regions via pointers $i$ and $j$:

- $i$ = last index of values $\le x$ (region $[p..i]$)
- $[i+1..j-1]$ = range of values $> x$
- $j$ = first index of unexamined (undetermined) values
- $r$ = position of the pivot $x$
  At each step, the current undetermined element $A[j]$ is compared with pivot $x$.
