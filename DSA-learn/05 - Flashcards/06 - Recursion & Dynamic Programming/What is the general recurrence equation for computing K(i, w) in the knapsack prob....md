---
title: "What is the general recurrence equation for computing K(i, w) in the knapsack prob..."
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
  - "What is the general recurrence equation for computing K(i, w) in the knapsack prob..."
---

# 🎴 What is the general recurrence equation for computing K(i, w) in the knapsack prob...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: What is the general recurrence equation for computing $K(i, w)$ in the knapsack problem without repetition? #card

?
Since we do not know in advance whether item $i$ is present or not in the optimal solution, we evaluate both options and select the best choice (the one that maximizes value):

$$

K(i, w) = \max \begin{cases} K(i-1, w) \\ v_i + K(i-1, w - w_i) & \text{if } w_i \le w \end{cases}

$$

⚠️ Note:
If item $i$ has a weight exceeding the current capacity ($w_i > w$), it cannot be placed in the knapsack and setting $K(i, w) = K(i-1, w)$ is mandatory.
