---
title: "How is the recursive algorithm for Fibonacci numbers defined and what is its compu..."
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
  - "How is the recursive algorithm for Fibonacci numbers defined and what is its compu..."
---

# 🎴 How is the recursive algorithm for Fibonacci numbers defined and what is its compu...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is the recursive algorithm for **Fibonacci** numbers defined and what is its **computational cost**? #card

?
Fibonacci function:

$$
f(n) = \begin{cases} 1 & \text{if } n = 0 \text{ or } n = 1 \\ f(n-1) + f(n-2) & \text{otherwise} \end{cases}
$$

Pseudocode:

```text
fib(n)
    if n = 0 or n = 1
        then return 1
    else return fib(n - 1) + fib(n - 2)
```

**Computational cost:**
The recurrence equation for the number of calls $T(n)$ is:

$$
T(n) = \begin{cases} 1 & \text{if } n = 0, 1 \\ 1 + T(n - 1) + T(n - 2) & \text{otherwise} \end{cases}
$$

Using the **iterative method**, the bounds are derived:

**Show steps**

$$
T(n) = \underbrace{1}_{\text{current call}} + \underbrace{T(n - 1) + T(n - 2)}_{\text{recursive calls}}
$$

For the **Upper Bound ($O$)**, knowing that $T(n-1) = 1 + T(n-2) + T(n-3) \ge 1 + T(n-2)$, we can substitute and approximate upwards:

$$
T(n) = T(n-1) + \underbrace{1 + T(n-2)}_{\le T(n-1)} \le 2T(n-1)
$$

Expanding successive iterations by substitution:

$$
\begin{aligned}
T(n) &\le 2T(n-1) \\
&\le 2 \cdot 2T(n-2) = 2^2 T(n-2) \\
&\le 2^2 \cdot 2T(n-3) = 2^3 T(n-3) \\
&\ \ \vdots \\
&\le 2^i T(n-i)
\end{aligned}
$$

We stop when the argument reaches the outer known base case for the inequality, namely when $n - i = 2 \implies i = n - 2$:

$$
\begin{aligned}
T(n) &\le 2^{n-2} T(2) \\
&\le 2^{n-2} \cdot 4 \\
&= 2^{n-2} \cdot 2^2 = 2^n \implies \mathbf{O(2^n)}
\end{aligned}
$$

For the **Lower Bound ($\Omega$)**, approximating downwards and ignoring the positive constant $1$, we derive $T(n) \ge 2T(n-2)$. Expanding successive iterations two steps at a time:

$$
\begin{aligned}
T(n) &\ge 2T(n-2) \\
&\ge 2 \cdot 2T(n-4) = 2^2 T(n-4) \\
&\ge 2^2 \cdot 2T(n-6) = 2^3 T(n-6) \\
&\ \ \vdots \\
&\ge 2^i T(n-2i)
\end{aligned}
$$

The stopping condition varies depending on the parity of $n$:

If $n$ is **even**, the inequality stops at $T(0)$ for $n - 2i = \bbox[orange, 5px, border: 1px dashed red]{0} \implies i = \frac{n}{2}$:

$$
T(n) \ge 2^{n/2} T(0) = 2^{n/2} \cdot 1 = \mathbf{2^{n/2}}
$$

If $n$ is **odd**, the inequality stops at $T(1)$ for $n - 2i = \bbox[orange, 5px, border: 1px dashed red]{1} \implies i = \frac{n-1}{2}$:

$$
T(n) \ge 2^{(n-1)/2} T(1) = 2^{(n-1)/2} \cdot 1 = 2^{-1/2} \cdot 2^{n/2} \implies \mathbf{\Omega(2^{n/2})}
$$

- **Upper bound ($O$): approximating $T(n-2)$ upwards with $T(n-1)$, we have $T(n) \le 2T(n-1) \implies \dots \le 2^i T(n-i) \implies 2^{n-1} \cdot T(1) \implies \mathbf{O(2^n)}$.**
- **Lower bound ($\Omega$): approximating $T(n-1)$ downwards with $T(n-2)$, we have $T(n) \ge 2T(n-2) \implies \dots \ge 2^i T(n-2i) \implies 2^{n/2} \cdot T(0) \implies \mathbf{\Omega(2^{n/2})}$.**Since both the upper and lower bounds are exponential, the cost is $T(n) \in \mathbf{\Theta(2^n)}$.

📌 Note: because of the exponential cost, to compute Fibonacci efficiently, a **bottom-up iterative** approach requiring linear time is preferred.
