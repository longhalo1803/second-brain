---
title: "(Fibonacci Recurrence) Using the substitution method, prove upper and lower bounds..."
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
  - "(Fibonacci Recurrence) Using the substitution method, prove upper and lower bounds..."
---

# 🎴 (Fibonacci Recurrence) Using the substitution method, prove upper and lower bounds...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 (Fibonacci Recurrence) Using the substitution method, prove upper and lower bounds for the Fibonacci recurrence equation

$$

T(n) = \begin{cases} 1 & \text{if } n = 0, 1 \\ T(n - 1) + T(n - 2) + 1 & \text{if } n \ge 2\end{cases}

$$

#card
?
****Upper bound****. We want to prove that $T(n) \in O(2^n)$, that is there exist $c > 0$ and $n_0 \ge 0$ such that $T(n) \le c2^n$ for all $n \ge n_0$. We proceed by induction:
**Base Case**:
$T(0) = 1 \le c \cdot 2^0 = c$ for any $c \ge 1$;
$T(1) = 1 \le c \cdot 2^1$ for any $c \ge 1/2$;
**Inductive Hypothesis**:
There exist $n_0 = 0$ and $c = 1$ such that, for all $k = 0, \dots, n - 1$, it holds that $T(k) \le 2^k$.
**Inductive Step**:
First, we use the recursive formula given by the recurrence equation to rewrite the term $T(n)$, with $n \ge 2$ (since for $n = 0, 1$ the expression of $T(n)$ is not recursive), and subsequently the inductive hypothesis on the terms $T(\cdot)$ calculated on values strictly smaller than $n$.

```text
{aligned} T(n)                       // = T(n - 1) + T(n - 2)
    // we can use the inductive hypothesis for T(n - 1) and T(n - 2)
// ≤ 2^{n-1} + 2^{n-2} + 1, we use 1 ≤ 2^{n-2} which is true for n ≥ 2
// ≤ 2 2^{n-2} + 2^{n-2} + 2^{n-2}
// = 4 2^{n-2} = 2^2 2^{n-2} = 2^n. {aligned}
```

****Lower bound****. We want to prove that $T(n) \in \Omega(2^{\frac{n}{2}})$, that is there exist $c > 0$ and $n_0 \ge 0$ such that $T(n) \ge c2^{\frac{n}{2}}$ for all $n \ge n_0$. We proceed by induction:
**Base Case**:
$T(0) = 1 \ge c \cdot 2^0 = c$ for any $c \le 1$;
$T(1) = 1 \ge c \cdot 2^{1/2} = c\sqrt{2}$ for any $c \le 1/\sqrt{2}$.
**Inductive Hypothesis**:
There exist $n_0 = 0$ and $c = 1/\sqrt{2}$ such that, for all $k = 1, \dots, n - 1$, it holds that $T(k) \ge c2^{\frac{k}{2}}$.
**Inductive Step**:
We proceed similarly to the case of the upper bound, assuming $n \ge 3$ and

```text
{aligned} T(n)                       // = T(n - 1) + T(n - 2) + 1
    // we can use the inductive hypothesis for T(n - 1) and T(n - 2)
// ≥ c2^{{n-1}{2}} + c2^{{n-2}{2}}
// = c2^{{n-2}{2}} (2^{{1}{2}} + 1)
    // since 2^{{1}{2}} = {2} > 1 we have 2^{{1}{2}} + 1 > 2
// ≥ c2^{{n}{2}-1} 2
// = c2^{{n}{2}} {aligned}
```
