---
title: "Exercise 1 (2)"
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
  - "Exercise 1 (2)"
---

# 🎴 Exercise 1 (2)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝 **Exercise 1**

Fibonacci numbers are recursively defined as follows:

$$

Fib(n)=\begin{cases}1 & \text{if } n=0 \\ 1 & \text{if } n=1 \\ Fib(n-1)+Fib(n-2) & \text{otherwise}\end{cases}

$$

Previously, a recursive algorithm with computational cost $\Theta(2^{n})$ to compute $Fib(n)$ was presented.
Provide in pseudocode an iterative version (that is, one that does not use recursion) with computational cost $\Theta(n)$.

💡 **Hint**Compute the n-th Fibonacci number starting "from the bottom", namely compute $Fib(2)$ using $Fib(0)$ and $Fib(1)$, then $Fib(3)$ using $Fib(1)$ and $Fib(2)$, then $Fib(4)$ using $Fib(2)$ and $Fib(3)$, and so on until reaching $Fib(n)$ computed using $Fib(n-2)$ and $Fib(n-1)$. #card
?
The simple cases to solve are $n=0, 1$. In the other cases, we compute the n-th Fibonacci number by iteratively computing those that precede it.

```text
IterativeFibonacci(n)
    if (n = 0 OR n = 1) then return 1
    F := 0
    f_1 := 1
    f_2 := 1
    for i := 2 to n do
        F := f_1 + f_2
        f_2 := f_1
        f_1 := F
    return F
```

**Remark on the cost:** The cost $\Theta(n)$ is exponential in the input size (which is $\log n$, that is, the number of bits needed to represent the number $n$ given as input).
