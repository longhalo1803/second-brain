---
title: "What is the greedy approach and what is its general execution strategy"
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
  - "What is the greedy approach and what is its general execution strategy"
---

# 🎴 What is the greedy approach and what is its general execution strategy

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the _greedy_ approach and what is its general execution strategy? #card

?
The greedy approach applies to optimization problems where one needs to select elements satisfying a certain property, with the goal of optimizing the associated overall cost.

General approach:

- **Sorting:** the objects of the problem are ordered according to their _'attractiveness'_ to be part of the optimal solution.
- **Incremental selection (_greedy_ choice):** the solution is generated incrementally, iteratively choosing the most attractive object among those not yet selected.
  Key characteristics of _greedy_ choices:

- At each iteration, the greedy choice provides the best solution at that moment (**local optimum**).
- Greedy choices **are never modified later** (no backtracking).
- After each iteration, the computed partial solution becomes "larger" and the rest of the solution is computed on a reduced-size subproblem.
