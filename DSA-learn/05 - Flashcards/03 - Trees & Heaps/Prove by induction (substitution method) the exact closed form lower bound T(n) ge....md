---
title: "Prove by induction (substitution method) the exact closed form lower bound T(n) ge..."
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Prove by induction (substitution method) the exact closed form lower bound T(n) ge..."
---

# 🎴 Prove by induction (substitution method) the exact closed form lower bound T(n) ge...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Prove by induction (**substitution method**) the exact closed form lower bound $T(n) \ge \lfloor 3^{n/2} \rfloor$ for the equation:

$$

T(n) = \begin{cases} 1 & \text{if } n \le 1 \\ 3[T(n-1) + 1] & \text{if } n > 1 \end{cases}

$$

#card
?
**Base Case:**
For $n=1$: $T(1) = 1 \ge \lfloor 3^{1/2} \rfloor = \lfloor 1.732 \rfloor = 1$. The base case is verified.

**Inductive Hypothesis:**
For all $k 1$):**
We must prove that the inductive hypothesis holds also for $k = n$, that is $T(n) \ge \lfloor 3^{n/2} \rfloor$. To do so, we first use the definition given by the recurrence equation to rewrite the term $T(n)$ for $n > 1$ and, subsequently, the inductive hypothesis on the term $T(\cdot)$ for a value smaller than $n$:
We substitute into the equation:

$$

\begin{aligned} T(n) &= 3[T(n-1) + 1] \\ &\ge 3\big[\lfloor 3^{(n-1)/2} \rfloor + 1\big] \end{aligned}

$$

Eliminating the floor function (knowing that adding +1 inside and subsequent multiplication will maintain the valid inequality):

$$

\begin{aligned} &\ge 3(3^{(n-1)/2} - 1 + 1) \\ &= 3 \cdot 3^{(n-1)/2} \\ &= 3^{1 + (n-1)/2} \\ &= 3^{(n+1)/2} \ge 3^{n/2} \ge \lfloor 3^{n/2} \rfloor \end{aligned}

$$

The inductive step is proved.
