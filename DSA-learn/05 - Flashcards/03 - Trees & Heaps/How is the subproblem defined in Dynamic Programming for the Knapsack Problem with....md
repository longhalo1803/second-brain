---
title: "How is the subproblem defined in Dynamic Programming for the Knapsack Problem with..."
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "How is the subproblem defined in Dynamic Programming for the Knapsack Problem with..."
---

# 🎴 How is the subproblem defined in Dynamic Programming for the Knapsack Problem with...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is the subproblem defined in Dynamic Programming for the Knapsack Problem **with repetition**? #card

?
Since the problem exhibits optimal substructure, the subproblem is parameterized by the capacity of the knapsack.

**Definition of the subproblem:**
For each integer capacity $w \in \mathbb{N}$ such that $0 \le w \le W$, we define:

$$

K(w) = \text{maximum value achievable with a knapsack of capacity } w

$$

⚠️ Note: since the weights $w_i$ are integers, it is sufficient to consider only discrete **integer values of $w$** in the interval $[0, W]$.

The solution to the original problem will correspond to the value of **$K(W)$**.

Read also: https://www.hello-algo.com/en/chapter_dynamic_programming/unbounded_knapsack_problem/#1453-coin-change-problem-ii
