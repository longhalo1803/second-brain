---
title: "What are the base case and the order of solving subproblems for the Knapsack with..."
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
  - "What are the base case and the order of solving subproblems for the Knapsack with..."
---

# 🎴 What are the base case and the order of solving subproblems for the Knapsack with...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What are the base case and the order of solving subproblems for the Knapsack with repetition? #card

?
**Base case:**
If the capacity $w$ is less than the weight of the lightest available item, no item can be placed in the knapsack:

$$
w  0 \implies w - w_i < w$).

📌 Remember: $K(w) = \text{maximum value achievable with a knapsack of capacity } w$.
$$
