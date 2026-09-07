---
title: "What are the base cases and where is the final solution found in the DP table for..."
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What are the base cases and where is the final solution found in the DP table for..."
---

# 🎴 What are the base cases and where is the final solution found in the DP table for...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What are the base cases and where is the final solution found in the DP table for knapsack without repetition? #card

?
**Base Cases (Initialization):**

- **First row (**$i=0$**):** $K(0, w) = 0 \quad \forall w = 0, 1, \dots, W$
  _(With no items available, the maximum achievable value is 0)_.
- **First column (**$w=0$**):** $K(i, 0) = 0 \quad \forall i = 0, 1, \dots, n$
  _(With zero knapsack capacity, the maximum achievable value is always 0)_.
  The **solution** to the original problem (considering all $n$ available items with total capacity $W$) is located in the bottom-right corner of the matrix:

$$

K(n, W)

$$
