---
title: "Exercise 6"
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
  - "Exercise 6"
---

# 🎴 Exercise 6

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: 📝 **Exercise 6**

Write a procedure that, given an integer $n\ge1$ as input, prints FIRST the list of all EVEN integer numbers between 1 and $n$, and AFTER the list of all ODD integer numbers between 1 and $n$.
Example: if $n=6$, the procedure prints first 2,4,6 and after 1,3,5. Provide an iterative version and a recursive version of it.

💡 **Hint**For the recursive procedure: define a recursive procedure that, given a natural number $n$, prints it if it is $>0$ and calls itself with input $n-2$. #card
?
We can slightly modify the sequential print procedure from Exercise 5: once $i$ is printed, the next number to print is not $i+1$, but $i+2$. In this way, if the main call is made with $i$ even, all even numbers between $i$ and $n$ will be printed; if, instead, the call is made with $i$ odd, all odd numbers between $i$ and $n$ will be printed.

To obtain the required result, it is necessary to introduce a main function $\textsf{Print_Lists}$ that contains the appropriate calls to the modified recursive procedure $\textsf{Print_next}$:

```text
Print_Lists(n)
    Print_next(2, n)
    Print_next(1, n)
```

```text
Print_next(i, n)
    if i ≤ n then
        print i
        Print_next(i+2, n)
```

In this case, a single main recursive call is not indicated, because the problem is solved by invoking $\textsf{Print_Lists(n)}$, which is not recursive itself (but invokes twice the recursive procedure $\textsf{Print_next}$, with different and appropriate parameters: first with $i=2$ to obtain the even numbers, then with $i=1$ to obtain the odd numbers).
