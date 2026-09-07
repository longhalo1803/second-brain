---
title: "Prove an upper bound (O) and a lower bound (Omega) using the iterative method for..."
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
  - "Prove an upper bound (O) and a lower bound (Omega) using the iterative method for..."
---

# 🎴 Prove an upper bound (O) and a lower bound (Omega) using the iterative method for...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝 Prove an upper bound ($O$) and a lower bound ($\Omega$) using the **iterative method** for the **Fibonacci** recurrence relation:

$$

T(n) = \begin{cases} 0 & \text{if } n = 0, 1 \\ 2 & \text{if } n = 2 \\ T(n-1) + T(n-2) + 2 & \text{if } n > 2 \end{cases}

$$

#card
?
Replacing the $T(\cdot)$ terms with their definition leads to an explosion in the number of terms that quickly becomes unmanageable, since each time the number of $T(\cdot)$ terms doubles. To realize this, a few iterations suffice:

$$

\begin{aligned}
T(n) &= T(n - 1) + T(n - 2) + 2 \\
&= [T(n - 2) + T(n - 3) + 2] + [T(n - 3) + T(n - 4) + 2] \\
&= T(n - 2) + 2T(n - 3) + T(n - 4) + 4 \\
&= [T(n - 3) + T(n - 4) + 2] + 2[T(n - 4) + T(n - 5) + 2] + [T(n - 3) + T(n - 5) + 2] + 4 \\
&= 2T(n - 3) + 2T(n - 4) + 2T(n - 5) + 8
\end{aligned}

$$

Notice, however, that the function $T(n)$ is always non-negative, and that for every $n \ge 3$

$$

T(n - 1) = T(n - 2) + T(n - 3) + 2 \ge T(n - 2) + 2.

$$

Therefore:

- to derive an upper bound for $T(n)$, we can exploit the fact that

$$

T(n) = T(n - 1) + T(n - 2) + 2 \le 2T(n - 1)

$$

- to derive a lower bound for $T(n)$, we can exploit the fact that

$$

T(n) = T(n - 1) + T(n - 2) + 2 \ge 2T(n - 2) + 4 \ge 2T(n - 2)

$$

We can then proceed separately to determine the upper and lower bounds using the iterative method.

**Upper Bound ($O$):**
Upper bounding: $T(n-2) \le T(n-1)$.

$$

\begin{aligned} T(n) &= T(n-1) + T(n-2) + 2 \\ &\le 2T(n-1) \\ &\le 2(2T(n-2)) = 2^2 T(n-2) \\ &\dots \\ &\le 2^i T(n-i) \end{aligned}

$$

Base case for $n-i = 2 \implies i = n-2$:

$$

T(n) \le 2^{n-2}T(2) = 2^{n-2} \cdot 2 = 2^{n-1} \implies T(n) \in O(2^n)

$$

**Lower Bound ($\Omega$):**
Lower bounding: $T(n-1) \ge T(n-2)$.

$$

\begin{aligned} T(n) &= T(n-1) + T(n-2) + 2 \\ &\ge 2T(n-2) + 4 \ge 2T(n-2) \\ &\ge 2(2T(n-4)) = 2^2 T(n-4) \\ &\dots \\ &\ge 2^i T(n-2i) \end{aligned}

$$

Assuming $n$ is even (this case is sufficient to determine a lower bound), the term $T(n − 2i)$ becomes the base case when $n-2i = 2$. We evaluate the lower bound for $i = n/2 − 1$:

$$

T(n) \ge 2^{\frac{n}{2}-1}T(2) = 2^{\frac{n}{2}} \implies T(n) \in \Omega\left(2^{n/2}\right)

$$

We can conclude by hypothesizing that $T(n)$ is exponential in $n$, i.e., that there exist two constants $c_1, c_2 > 0$ such that $c_1 2^{\frac{n}{2}} \le T(n) \le c_2 2^n$.
