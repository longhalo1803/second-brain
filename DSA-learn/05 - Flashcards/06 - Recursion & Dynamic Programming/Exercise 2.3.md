---
title: "Exercise 2.3"
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
  - "Exercise 2.3"
---

# 🎴 Exercise 2.3

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 2.3**

Given the recurrence equation:

$$

T(n) = \begin{cases} \Theta(1) & \text{if } n \le 1 \\ 7T(n/\alpha) + O(n) & \text{otherwise} \end{cases}

$$

State whether, and if so for which values of the parameter $\alpha \ge 0$, it is possible that $T(n) \in O(n \log n)$ by directly applying the **Master Theorem**. #card
?
Using the Master Theorem we have $a=7$, $b=\alpha$, and $d=1$. We must compare $\log_b a = \log_{\alpha} 7$ with $d=1$ and determine $\alpha$ so that the second condition of the theorem holds, since we are asking for $T(n) \in O(n \log n)$.

Therefore, we look for $\alpha$ such that $\log_{\alpha} 7 = 1$. The value we are looking for is $\alpha = 7$. Indeed:

$$

\begin{aligned} \log*{\alpha} 7 &= 1 \\ \alpha^{\log*{\alpha} 7} &= \alpha^1 \\ 7 &= \alpha \end{aligned}

$$

(or by definition of logarithm $\log_\alpha 7 = 1 \iff \alpha^1=7$)
