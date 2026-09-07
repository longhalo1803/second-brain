---
title: "What is the computational cost of the recursive algorithm for calculating the fact..."
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
  - "What is the computational cost of the recursive algorithm for calculating the fact..."
---

# 🎴 What is the computational cost of the recursive algorithm for calculating the fact...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: What is the **computational cost** of the recursive algorithm for calculating the **factorial**? #card

?
Factorial function:

$$
f(n) = \begin{cases} 1 & \text{if } n = 1 \;\;\;\;\;\;\; \small\text{🡠 base case}\\ n \cdot f(n-1) & \text{otherwise}\;\;\;\; \small\text{🡠 recursive case} \end{cases}
$$

Pseudocode:

```text
fact(n)
    if n = 1                             // base case
        then return 1
    else return n * fact(n - 1)          // recursive case
```

**Computational cost:**
We can write $T(n)$ by exploiting the recursive nature of the function **`fact(n)`**.

- If $n=1$, then the function executes the instruction in the **`then`** branch, terminating after executing only one logical operation.
- Otherwise, it executes an arithmetic operation and subsequently all those executed by **`fact(n-1)`**.
  The recurrence equation for the running time is:

$$
T(n) = \begin{cases} 1 & \text{if } n = 1 \\ 1 + T(n - 1) & \text{otherwise} \end{cases}
$$

We can obtain a closed-form formula using the **iterative method**:

```text
{aligned}T(n)                        // = 1 + T(n-1)
// = 1 + 1 + T(n-2) = 2 + T(n-2)
// =
    // = i + T(n-i) 🡠 at the generic step i{aligned}
```

When we reach the last step, i.e. $i = n - 1$, we obtain:

$$
T(n) = (n - 1) + T(1) = n
$$

Therefore $T(n) \in O(n)$.

⚠️ **Warning**:
The algorithm performs $O(n)$ operations (linear), but it is NOT linear with respect to the input size!
The input size (number of bits to represent $n$) is $\log_2 n$. If the number of bits is $b = \log_2 n$, then $n = 2^b$.
Consequently, the computational cost relative to the input size in bits (which is what we care about since **`fact(n)`** takes a single number as input) is **exponential**.
