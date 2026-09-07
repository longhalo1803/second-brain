---
title: "Exercise 2.5"
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
  - "Exercise 2.5"
---

# 🎴 Exercise 2.5

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 2.5**

Given the recurrence equation:

$$

T(n) = \begin{cases} \Theta(1) & \text{if } n \le 1 \\ 2T(n/3) + O(n^{\alpha+1}) & \text{otherwise} \end{cases}

$$

State whether, and if so for which values of the parameter $\alpha \ge 0$, it is possible that $T(n) \in O(n \log n)$ by directly applying the **Master Theorem**. #card
?
Using the Master Theorem we have $a=2$, $b=3$, and $d=\alpha+1$. We must compare $\log_b a = \log_3 2 < 1$ with $d=\alpha+1$.

For the desired $T(n)$ to hold, the only alternative for direct application would be for the second condition to hold with $d=\log_3 2$. Thus, we look for $\alpha \ge 0$ such that $\alpha+1 = \log_3 2$, which means $\alpha = \log_3 2 - 1 < 0$. We conclude that **no such $\alpha$ exists** via pure and direct application.

**Remark:** If we chose $\alpha = 0$, we would get $T(n) = O(n)$, which in turn is $O(n \log n)$. Compared to the previous solution, we did not obtain the required bound directly from the application of the theorem, but with an additional consideration.
