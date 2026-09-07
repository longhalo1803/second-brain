---
title: "Exercise 2.2"
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
  - "Exercise 2.2"
---

# 🎴 Exercise 2.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 2.2**

Given the recurrence equation:

$$

T(n) = \begin{cases} \Theta(1) & \text{if } n \le 1 \\ 4T(n/4) + O(n^{\alpha+1}) & \text{otherwise} \end{cases}

$$

State whether, and if so for which values of the parameter $\alpha \ge 0$, it is possible that $T(n) \in O(n^2)$ by directly applying the **Master Theorem**. #card
?
Using the Master Theorem we have $a=4$, $b=4$, and $d=\alpha+1$.

We must compare $\log_b a = \log_4 4 = 1$ with $d=\alpha+1$ and, to get the desired $T(n^2)$, the only option is for the first condition to hold and $d=2$.

Indeed, if the third condition held, we would have $T(n) \in O(n)$; if the second held, we would have $T(n) = O(n \log n)$ (and $\alpha$ would have to be $=0$).

Therefore, for the first condition to hold, it must be $\log_4 4 = 1 0$ and the theorem tells us we can claim $T(n) \in O(n^d)$.
Since we want $T(n) \in O(n^2)$, we just need to find $\alpha$ such that $d = \alpha+1 = 2$.
Thus, the value we are looking for is $\alpha = 1$.
