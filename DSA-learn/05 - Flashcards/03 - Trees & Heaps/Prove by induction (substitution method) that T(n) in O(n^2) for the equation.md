---
title: "Prove by induction (substitution method) that T(n) in O(n^2) for the equation"
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
  - "Prove by induction (substitution method) that T(n) in O(n^2) for the equation"
---

# 🎴 Prove by induction (substitution method) that T(n) in O(n^2) for the equation

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Prove by induction (**substitution method**) that $T(n) \in O(n^2)$ for the equation:

$$

T(n) = \begin{cases} 1 & \text{if } n = 0, 1 \\ T(n-2) + 2n & \text{if } n > 1 \end{cases}

$$

#card
?
We must prove that there exist $c > 0$ and $n_0 \ge 0$ such that $T(n) \le cn^2$ for all $n \ge n_0$.
Starting to evaluate the claim for $n = 0$, we realize that there is no constant $c > 0$ for which $T(0) = 1 ≤
c · 0 = 0$, so this case cannot be used as a base case.

**Base Case:**
For $n=0$: $T(0) = 1 \le c \cdot 0^2 = 0$ (False, so $n_0$ cannot be 0).
For $n=1$: $T(1) = 1 \le c \cdot 1^2 \quad\forall c \ge 1$.
For $n=2$: $T(2) = 4 \le c \cdot 2^2 \implies 4 \le 4c \quad\forall c \ge 1$. We fix $n_0 = 1$.

**Inductive Hypothesis:**
Strong induction: There exist a constant $c \geq 1$ and a value $n_0 = 1$ such that, for all $k = 1, \dots , n - 1$, we have $T(k) ≤ ck^2$.
(Weak induction: We assume it holds for $n-2$, i.e. $T(n-2) \le c(n-2)^2$)

**Inductive Step ($n \ge 3$):**
First, we use the definition given by the recurrence equation to rewrite the term $T(n)$ for $n \ge 3$ and, subsequently, the inductive hypothesis on the term $T(\cdot)$ calculated on a value smaller than $n$:

```text
{aligned} T(n)                       // = T(n - 2) + 2n
    // since n ≥ 3, we have n - 2 ≥ 1 and we can use the inductive hypothesis for T(n - 2)
// ≤ c(n - 2)^2 + 2n
// = cn^2 + 2n(1 - 2c) + 4c
    // there exists a value of c compatible with the inductive hypothesis such that we can conclude...
// ≤ cn^2? {aligned}
```

For it to be $\le cn^2$, it must hold that $2n(1-2c) + 4c \le 0$, that is $n \ge \frac{2c}{2c-1}$. Since $c \ge 1$, the fraction $\frac{2c}{2c-1}$ is $\le 2$.
Being in the inductive step with $n \ge 3$, the condition $n \ge 2$ is always satisfied. We have proved the claim.

Alternative: we must prove that there exists a $c \ge 1$ such that $cn^2 + 2n(1 - 2c) + 4c \le cn^2$, that is such that $n(1 - 2c) + 2c \le 0$, that is (since $1 - 2c \le 0$) such that $n \ge \frac{2c}{2c-1}$.
Since, for any $c \ge 1$ we have that $1 < \frac{2c}{2c-1} \le 2$, and, given that in the inductive step we are assuming $n \ge 3$, any value of $c$ greater than or equal to one allows us to draw the desired conclusion.
Thus, we have proved that for any constant $c \ge 1$ and for any $n \ge n_0 = 1$ we have $T(n) \le cn^2$.
