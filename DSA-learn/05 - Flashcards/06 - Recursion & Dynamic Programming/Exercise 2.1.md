---
title: "Exercise 2.1"
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
  - "Exercise 2.1"
---

# 🎴 Exercise 2.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 2.1**

Given the recurrence equation:

$$

T(n) = \begin{cases} \Theta(1) & \text{if } n \le 1 \\ 8T(n/\alpha) + O(n^{2.5}) & \text{otherwise} \end{cases}

$$

State whether, and if so for which values of the parameter $\alpha \ge 0$, it is possible that $T(n) \in O(n^{2.5} \log n)$ by directly applying the **Master Theorem**. #card
?
Using the Master Theorem we have $a=8$, $b=\alpha$, and $d=2.5$.

We must compare $\log_b a = \log_{\alpha} 8$ with $d=2.5$ and, for the desired $T(n)$ to hold, the second condition of the theorem must be satisfied. Therefore, we look for $\alpha$ such that:

$$

\begin{aligned} \log*{\alpha} 8 &= 2.5 \\ \alpha^{\log*{\alpha} 8} &= \alpha^{2.5} \\ 8 &= \alpha^{2.5} \\ (8)^{\frac{1}{2.5}} &= (\alpha^{2.5})^{\frac{1}{2.5}} \\ 8^{\frac{1}{2.5}} &= \alpha \end{aligned}

$$

The value of $\alpha$ we are looking for is $\alpha = 8^{\frac{1}{2.5}}$.
