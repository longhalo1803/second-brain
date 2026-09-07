---
title: "In the knapsack problem without repetition, what is the formulation of K(i, w) in..."
tags:
  - dsa
  - flashcards
  - clrs
  - dynamic-programming
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "In the knapsack problem without repetition, what is the formulation of K(i, w) in..."
---

# 🎴 In the knapsack problem without repetition, what is the formulation of K(i, w) in...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: In the knapsack problem without repetition, what is the formulation of $K(i, w)$ in CASE 2, i.e., when item $i$ BELONGS to the optimal solution? #card

?
If item $i$ **belongs** to the optimal solution for the subproblem $K(i, w)$, the knapsack capacity must be sufficient ($w_i \le w$).

In this case, the recurrence formula is:

$$

K(i, w) = v_i + K(i-1, w - w_i)

$$

• $v_i$: value of item $i$ obtained by placing it in the knapsack;
• $K(i-1, w - w_i)$: maximum value achievable with the first $i-1$ items
and remaining capacity $w - w_i$
