---
title: "In the knapsack problem without repetition, what is the formulation of K(i, w) in..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "In the knapsack problem without repetition, what is the formulation of K(i, w) in..."
---

# 🎴 In the knapsack problem without repetition, what is the formulation of K(i, w) in...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: In the knapsack problem without repetition, what is the formulation of $K(i, w)$ in CASE 1, i.e., when item $i$ DOES NOT belong to the optimal solution? #card

?
If item $i$ **does not belong** to the optimal solution for the subproblem with items chosen from $\{1, \dots, i\}$ and capacity $w$, the maximum achievable value equals the value obtained without considering item $i$:

$$
K(i, w) = K(i-1, w)
$$

Since item $i$ is not put into the knapsack, the available capacity remains unchanged ($w$) and the best candidate must be sought among the first $i-1$ items.
