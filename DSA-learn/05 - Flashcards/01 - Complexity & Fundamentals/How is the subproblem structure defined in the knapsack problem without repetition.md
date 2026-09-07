---
title: "How is the subproblem structure defined in the knapsack problem without repetition"
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
  - "How is the subproblem structure defined in the knapsack problem without repetition"
---

# 🎴 How is the subproblem structure defined in the knapsack problem without repetition

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: How is the subproblem structure defined in the knapsack problem **without** repetition? #card

?
In the knapsack problem **without repetition**, each item can be chosen at most once.
Consequently, in subproblems we must also keep track of items already considered.

A subproblem is characterized by two parameters:

- A **reduced subset of items**: being able to choose only among the first $i$ items $\{1, 2, \dots, i\}$
- A **reduced capacity** of the knapsack: $w \le W$
  We define the subproblem function $K(i, w)$:

$$
K(i, w) = \text{maximum value achievable when choosing only among items } 1, 2, \dots, i \text{ with a knapsack of capacity } w \le W
$$

📌 Note:
Unlike the knapsack _with repetition_ (where the single variable $K(w)$ was sufficient), in the knapsack without repetition the first dimension $i$ is indispensable to ensure that each item is selected at most once.
📌 Note 2:
The convention $K(i, w)$ is used instead of $K(w, i)$ for efficiency and practical reasons explained later.
