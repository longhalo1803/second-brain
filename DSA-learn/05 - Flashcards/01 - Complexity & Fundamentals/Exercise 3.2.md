---
title: "Exercise 3.2"
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Exercise 3.2"
---

# 🎴 Exercise 3.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: 📝 **Exercise 3.2**

Given two positive integers $a$ and $n$, design a recursive algorithm for computing $a^n$ that has computational cost $O(\log n)$.

💡 **Hint**To apply Divide-and-Conquer, observe that:

$$
a^{n}=a^{\lceil n/2\rceil}\cdot a^{\lfloor n/2\rfloor}
$$

Furthermore, $a^{\lceil n/2\rceil}=a^{\lfloor n/2\rfloor}$ if $n$ is even, and $a^{\lceil n/2\rceil}=a\cdot a^{\lfloor n/2\rfloor}$ if $n$ is odd. #card
?
**Base case:** for $n=1$ we have $a^{n}=a^{1}=a$.
**Non-base case:** for $n>1$ we use the division property of Divide-and-Conquer.

```text
FastPower(a, i)
    if i = 1 then
        return a
    else
        x := FastPower(a, floor( i / 2 ) )
        if (i mod 2 = 0) then                // if i is even
            return x x
        else                                 // if i is odd
            return x x a
```

The main call will be $\textsf{FastPower(a, n)}$.

**Upper Bound on recursive calls:**
At each step, the value of $i$ is halved ($\lfloor i/2 \rfloor$). The maximum number of integer divisions to reach the base case $i=1$ starting from $n$ is upper bounded by $\lfloor \log_2 n \rfloor$. Consequently, the number of recursive calls invoked is $O(\log n)$. Since each call performs a constant number of operations ($O(1)$), the overall computational cost is bounded by $O(\log n)$.
