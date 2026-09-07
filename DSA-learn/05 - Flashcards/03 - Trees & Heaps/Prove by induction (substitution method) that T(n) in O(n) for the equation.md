---
title: "Prove by induction (substitution method) that T(n) in O(n) for the equation"
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
  - "Prove by induction (substitution method) that T(n) in O(n) for the equation"
---

# 🎴 Prove by induction (substitution method) that T(n) in O(n) for the equation

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Prove by induction (**substitution method**) that $T(n) \in O(n)$ for the equation:

$$

T(n) = \begin{cases} 0 & \text{if } n = 0 \\ T(n-1) + d & \text{if } n > 0 \end{cases}

$$

#card
?
We must prove that there exist $c > 0$ and $n_0 \ge 0$ such that $T(n) \le cn$ for all $n \ge n_0$.

**Base Case:**
$T(0) = 0 \le c \cdot 0$ for any constant $c > 0$,
$T(1) = 0 + d \le c \cdot 1 = c$ for any constant $c \geq d$.

**Inductive Hypothesis:**
Strong induction: There exist $n_0 = 0$ and $c \geq d$ such that, for all $k = n_0, \dots , n - 1$, it holds that $T(k) \leq ck$.
(Weak induction: We assume it holds for $n-1$, i.e. $T(n-1) \le c(n-1)$)

**Inductive Step:**
First, we use the recursive formula given by the recurrence equation to rewrite the term $T(n)$, with $n \ge 1$ (since for $n = 0$ the expression of $T(n)$ is not recursive), and subsequently the inductive hypothesis on the terms $T(\cdot)$ calculated on values strictly smaller than $n$:

```text
{aligned} T(n)                       // = T(n - 1) + d
    // use the inductive hypothesis for the term T(n - 1)
// ≤ c(n - 1) + d
// = cn - c + d
    // by inductive hypothesis we have c ≥ d, it holds that d - c ≤ 0 , so the term can be bounded by cn
// ≤ cn
    // :
T(n)                                 // = cn - c + d = cn + {(d - c)}_{≤ 0} ≤ cn {aligned}
```

Alternative: we want to prove that $cn - c + d \le cn$. Subtracting $cn$ from both sides we get $-c + d \le 0 \implies c \ge d$.
By fixing the constant $c \ge d$ and $n_0 = 1$, the inequality is always true. Therefore $T(n) \in O(n)$.

Also try the dual proof for the lower bound.
