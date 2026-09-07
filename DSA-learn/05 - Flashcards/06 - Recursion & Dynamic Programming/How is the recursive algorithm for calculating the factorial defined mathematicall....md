---
title: "How is the recursive algorithm for calculating the factorial defined mathematicall..."
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
  - "How is the recursive algorithm for calculating the factorial defined mathematicall..."
---

# 🎴 How is the recursive algorithm for calculating the factorial defined mathematicall...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: How is the recursive algorithm for calculating the **factorial** defined mathematically and in pseudocode?

How do the recursive calls work with, for example, $n=5$ (show all steps)? #card
?
The factorial of a natural number $n$ (denoted by $n!$) is the product of all positive integers less than or equal to $n$.
Examples:
$0! = 1$,
$1! = 1$,
$2! = 2 \cdot 1 = 2$,
$3! = 3 \cdot 2 \cdot 1 = 6$,
$4! = 4 \cdot 3 \cdot 2 \cdot 1 = 24$
The factorial function is defined mathematically as:

$$
f(n) = \begin{cases} 1 & \text{if } n = 1 \;\;\;\;\;\;\; \small\text{🡠 base case}\\ n \cdot f(n-1) & \text{otherwise}\;\;\;\; \small\text{🡠 recursive case} \end{cases}
$$

($n$ is the size of the original problem, $n-1$ that of the smaller subproblem on which recursion is invoked)

The corresponding pseudocode is:

```text
fact(n)
    if n = 1                             // base case
        then return 1
    else return n * fact(n - 1)          // recursive case
```

Review and visualization of recursion examples:
