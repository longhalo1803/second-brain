---
title: "Exercise 2.4"
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
  - "Exercise 2.4"
---

# 🎴 Exercise 2.4

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 2.4**

Given the recurrence equation:

$$

T(n) = \begin{cases} \Theta(1) & \text{if } n \le 1 \\ 2T(n/3) + O(n^{\alpha+\frac{1}{2}}) & \text{otherwise} \end{cases}

$$

State whether, and if so for which values of the parameter $\alpha \ge 0$, it is possible that $T(n) \in O(n)$ by directly applying the **Master Theorem**. #card
?
Using the Master Theorem we have $a=2$, $b=3$, and $d=\alpha+\frac{1}{2}$.

$T(n) \in \begin{cases} O(n^d) & \text{if } \log_b a d \quad \small\color{grey}\text{(Third Condition)} \end{cases}$

We must compare $\log_b a = \log_3 2 \log_3 2$ and, consequently, $d = 1 = \alpha + \frac{1}{2}$, from which we derive $\alpha = \frac{1}{2}$.
