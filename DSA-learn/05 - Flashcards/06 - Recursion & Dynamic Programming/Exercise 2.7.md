---
title: "Exercise 2.7"
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
  - "Exercise 2.7"
---

# 🎴 Exercise 2.7

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 2.7**

Given the recurrence equation:

$$

T(n) = \begin{cases} 1 & \text{if } n \le 1 \\ \alpha T(n/2) + n & \text{if } n > 1 \end{cases}

$$

State if, and for which values of the real parameter $\alpha \ge 0$, it is possible that $T(n) = O(n \log n)$ using the **Master Theorem**. #card
?
Using the Master Theorem, we deduce that the answer is **affirmative** provided that the second condition of the theorem is satisfied, namely $\log_2 \alpha = 1$, from which we immediately derive $\underbracket[0.5]{\,\alpha\,}_{2^{\log_2{\alpha}}} = 2^1 = 2$.
