---
title: "Exercise 2.10"
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
  - "Exercise 2.10"
---

# 🎴 Exercise 2.10

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 2.10**

Given the recurrence equation:

$$

T(n) = \begin{cases} 1 & \text{if } n \le 1 \\ 4T(n/\alpha) + n^3 & \text{if } n > 1 \end{cases}

$$

State if, and for which values of the real parameter $\alpha \ge 0$, it is possible that $T(n) = O(n^3 \log n)$ using the **Master Theorem**. #card
?
Using the Master Theorem, we deduce that the answer is **affirmative** provided that $\log_{\alpha} 4 = 3$, namely $\alpha = 4^{1/3}$.

Indeed, to use the second condition of the Master Theorem, we must have an exact equality between $\log_b a$ and $d$:

$$

\log\_{\alpha} 4 = 3

$$

From which:

$$

\begin{aligned} \alpha^{\log\_{\alpha} 4} &= \alpha^3 \\ 4 &= \alpha^3 \\ 4^{1/3} &= \alpha \end{aligned}

$$
