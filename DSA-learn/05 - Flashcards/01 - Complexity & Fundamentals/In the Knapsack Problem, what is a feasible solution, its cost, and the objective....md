---
title: "In the Knapsack Problem, what is a feasible solution, its cost, and the objective..."
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
  - "In the Knapsack Problem, what is a feasible solution, its cost, and the objective..."
---

# 🎴 In the Knapsack Problem, what is a feasible solution, its cost, and the objective...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: In the Knapsack Problem, what is a **feasible solution**, its **cost**, and the **objective function**? #card

?
Given an instance with capacity $W$ and items having weights $w_i$ and values $v_i$:

- **Feasible solution: **a selection of items $i_1, i_2, \dots, i_k$ with indices $i_t \in [1..n]$ such that the total weight does not exceed the capacity:

$$
\sum_{t=1}^{k} w_{i_t} \le W
$$

- **Cost (Value) of the solution: **is given by the sum of the values of the selected items:

$$
\sum_{t=1}^{k} v_{i_t}
$$

- **Objective function: **maximization of the total cost:

$$
\max \sum_{t=1}^{k} v_{i_t}
$$
