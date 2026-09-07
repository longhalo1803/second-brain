---
title: "Exercise 2.9"
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
  - "Exercise 2.9"
---

# 🎴 Exercise 2.9

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 2.9**

Given the recurrence equation:

$$

T(n) = \begin{cases} 1 & \text{if } n \le 1 \\ 8T(n/5) + n & \text{if } n > 1 \end{cases}

$$

State if, and for which values of the real parameter $\alpha \ge 0$, it is possible that $T(n) = O(n \log n)$ using the **Master Theorem**. #card
?
Using the Master Theorem, we deduce that the answer is **negative** since $T(n)=\Omega(n^{\log_{5}8})=\Omega(n^{1.29202967422})$.

Indeed, we would need

$$

\log\_{5}8 = 1

$$

in order to use the second condition of the Master Theorem and obtain the desired cost. It is not necessary to explicitly calculate the value of the logarithm to deduce that $\log_{5}8 \neq 1$.

Indeed, by definition of logarithm, $\log_{5}8$ is the exponent to which 5 must be raised to obtain 8. Since $5^{1}=5<8<5^{2}=25$, we have $1<\log_{5}8<2$ (in fact, the left-hand inequality is enough for us).
