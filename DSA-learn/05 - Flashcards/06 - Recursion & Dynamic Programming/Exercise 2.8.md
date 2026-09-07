---
title: "Exercise 2.8"
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
  - "Exercise 2.8"
---

# 🎴 Exercise 2.8

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 2.8**

Given the recurrence equation:

$$

T(n) = \begin{cases} 1 & \text{if } n \le 1 \\ 9T(n/\alpha) + n^{2.5} & \text{if } n > 1 \end{cases}

$$

State if, and for which values of the real parameter $\alpha \ge 0$, it is possible that $T(n) = O(n^3)$ using the **Master Theorem**. #card
?
Using the Master Theorem, we deduce that the answer is **affirmative** provided that $\log_{\alpha} 9 = 3$, namely $\alpha = 9^{1/3}$.
Indeed, we have $a=9$, $b=\alpha$, and $d=2.5$. In order to have $T(n) \in O(n^3)$, it is sufficient that $\log_{\alpha} 9 = 3 > 2.5$. In this way, using the third case of the Master Theorem, we have $T(n) = O(n^{\log_{\alpha} 9}) = O(n^3)$.

To find such $\alpha$, we raise $\alpha$ to $\log_{\alpha} 9$ and raise $\alpha$ to 3:

```text
{aligned} _{} 9                      // = 3
    ^{_{} 9}                             // = ^3 (*) using the definition of logarithm
    9                                    // = ^3 raise both sides to 1/3
9^{1/3}                              // = (^3)^{1/3}
9^{1/3}                              // = {aligned}
```

_(_) $\log_{\alpha} 9$ is that number to which $\alpha$ must be raised to get 9. Therefore, if we raise $\alpha$ to that number, we get exactly 9.*

**Remark:** besides the direct algebraic solution, the required asymptotic condition is also satisfied in the following alternative cases:
• **(a)** $\alpha > 9^{1/2.5}$, which derives from the condition $\log_{\alpha} 9 < 2.5$ (with similar calculations, keeping in mind that the logarithm is an increasing function). By the Master Theorem, we will have $T(n) \in O(n^{2.5}) \in O(n^3)$.
• **(b)** $\alpha = 9^{1/2.5}$, which derives from the condition $\log_{\alpha} 9 = 2.5$. We will have $T(n) \in O(n^{2.5} \log n) \in O(n^3)$, because $\log n \in O(n^{0.5})$.
• **(c)** $\alpha \ge 9^{1/2.5}$, which includes the two previous answers.
• **(d)** $\alpha \ge 9^{1/3}$, which derives from the condition $\log_{\alpha} 9 \le 3$ and includes all other answers, and furthermore, when $2.5 < \log_{\alpha} 9 \le 3$, we will have $T(n) \in O(n^{\log_{\alpha} 9}) \in O(n^3)$.
