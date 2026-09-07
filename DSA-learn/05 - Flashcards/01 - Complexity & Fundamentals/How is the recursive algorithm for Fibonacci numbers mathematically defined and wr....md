---
title: "How is the recursive algorithm for Fibonacci numbers mathematically defined and wr..."
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
  - "How is the recursive algorithm for Fibonacci numbers mathematically defined and wr..."
---

# 🎴 How is the recursive algorithm for Fibonacci numbers mathematically defined and wr...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: How is the recursive algorithm for **Fibonacci numbers** mathematically defined and written in pseudocode?

How do the recursive calls work for, for example, $n=5$ (show all steps)? #card
?
Fibonacci numbers form a mathematical sequence where each number is the sum of the two preceding ones: 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, ...
Fibonacci numbers are mathematically defined as:

$$
f(n) = \begin{cases} 1 & \text{if } n = 0 \text{ or } n = 1 \\ f(n-1) + f(n-2) & \text{otherwise} \end{cases}
$$

The pseudocode is:

```text
fib(n)
    if n = 0 or n = 1
        then return 1
        else return fib(n - 1) + fib(n - 2) // recursive calls
```

📌 Note on starting conventions for the sequence:
• **1, 1 convention** (used above)**:** with the conditions `if n = 0 or n = 1 return 1` (or `if n

```text
fib(n)
    if n ≤ 1
        then return n
        else return fib(n - 1) + fib(n - 2) // recursive calls
```
