---
title: "Solve the following recurrence relation using the iterative method"
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
  - "Solve the following recurrence relation using the iterative method"
---

# 🎴 Solve the following recurrence relation using the iterative method

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝 Solve the following recurrence relation using the **iterative method**:

$$

T(n) = \begin{cases} 1 & \text{if } n = 0, 1 \\ T(n-2) + 2n & \text{if } n > 1 \end{cases}

$$

#card
?
Proceeding mechanically as in the previous example:

$$

\begin{aligned}
T(n) &= T(n - 2) + 2n \\
&= [T(n - 4) + 2(n - 2)] + 2n = T(n - 4) + 4n - 4 \\
&= [T(n - 6) + 2(n - 4)] + 4n - 4 = T(n - 6) + 6n - 12 \\
&= [T(n - 8) + 2(n - 6)] + 6n - 12 = T(n - 8) + 8n - 24 \\
&= [T(n - 10) + 2(n - 8)] + 8n - 24 = T(n - 10) + 10n - 30, \\
&\dots \text{ after } i \text{ iterations}\dots \\
&= T(n - 2i) + 2i \cdot n - \alpha
\end{aligned}

$$

it is not immediately obvious how to express the constant term $\alpha$ (not depending on $n$) as a function of the number of iterations. Instead, proceeding with greater care, by successive iterations grouping the terms:

$$

\begin{aligned} T(n)
&= T(n - 2) + 2n \\
&= [T(n - 4) + 2(n - 2)] + 2n = T(n - 4) + 4n - 2 \cdot 2 \\
&= [T(n - 6) + 2(n - 4)] + 4n - 2 \cdot 2 = T(n - 6) + 6n - (2 \cdot 4 + 2 \cdot 2) \\
&= [T(n - 8) + 2(n - 6)] + 6n - (2 \cdot 4 + 2 \cdot 2) = T(n - 8) + 8n - (2 \cdot 6 + 2 \cdot 4 + 2 \cdot 2)\\
&= \dots \small\text{ after }i\text{ iterations} \\
&= T(n-2i) + 2in - \sum*{k=1}^{i-1} 2 \cdot 2k \\
&= T(n-2i) + 2in - 4\sum*{k=1}^{i-1}k \\
&= T(n-2i) + 2in - 4 \frac{(i-1)i}{2} \\
&= T(n-2i) + 2i(n-i+1) \end{aligned}

$$

**If $n$ is even**, the base case is $T(0)$ reached for $n-2i = 0 \implies i = n/2$:

$$

T(n) = T(0) + 2\frac{n}{2}\left(n - \frac{n}{2} + 1\right) = 1 + n\left(\frac{n}{2} + 1\right) = \frac{n^2}{2} + n + 1

$$

**If $n$ is odd**, the base case is $T(1)$ reached for $n-2i = 1 \implies i = (n-1)/2$:

$$

T(n) = 1 + 2\frac{n-1}{2}\left(n - \frac{n-1}{2} + 1\right) = \dots = \frac{n^2}{2} + n - \frac{1}{2}

$$
