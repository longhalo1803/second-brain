---
title: "Exercise 1"
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
  - "Exercise 1"
---

# 🎴 Exercise 1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 1**

Using the **Master Theorem**, give an asymptotic upper bound for the following equations, assuming that $T(1) \in \Theta(1)$:

1. $T(n) = 7T(n/4) + n$
2. $T(n) = 2T(n/2) + n^2$
3. $T(n) = 4T(n/2) + n$
4. $T(n) = 4T(n/2) + n^3$
5. $T(n) = 4T(n/3) + n^2$
6. $T(n) = 2T(n/3) + \sqrt{n}$
7. $T(n) = 16T(n/4) + n^2$ #card
   ?
   **Master Theorem**: Given a recurrence equation of the form:

$$

T(n) = \begin{cases} \Theta(1) & \text{if } n \le n_0 \\ aT(n/b) + O(n^d) & \text{otherwise} \end{cases}

$$

with constants $a \ge 1, b > 1, d \ge 0$, the asymptotic solutions are divided into three cases:

```text
T(n) ∈ {cases} O(n^d)                // if _b a  d {grey}(Third Condition) {cases}
```

We need to compare $\log_b a$ with $d$:

1. $a=7, b=4, d=1$.

Since $4^1 = 4 1 = d$, so the **Third Condition** applies: $T(n) \in O(n^{\log_4 7})$.

2. $a=2, b=2, d=2$.

Since $\log_2 2 = 1 1 = d$, the **Third Condition** applies: $T(n) \in O(n^2)$.

4. $a=4, b=2, d=3$.

Since $\log_2 4 = 2 1/2 = d$, in fact:

```text
{aligned} _3 2                       // > {1}{2}
2 _3 2                               // > 1
    _3 2^2                               // > 1 [c _b(a) = _b(a^c)]
_3 4                                 // > 1 {aligned}
```

the last inequality is true, and therefore the first one is too. Thus the **Third Condition** applies: $T(n) \in O(n^{\log_3 2})$.

7. $a=16, b=4, d=2$.
   Since $\log_b a = \log_4 16 = 2 = d$, the **Second Condition** applies: $T(n) \in O(n^2 \log n)$.
