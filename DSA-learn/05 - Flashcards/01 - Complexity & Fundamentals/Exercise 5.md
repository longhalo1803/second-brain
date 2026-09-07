---
title: "Exercise 5"
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
  - "Exercise 5"
---

# 🎴 Exercise 5

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: 📝 **Exercise 5**

Write a recursive procedure that, given an integer $n\ge1$ as input, prints the list of all integer numbers between 1 and $n$, i.e., 1,2,3,...,n.
Also provide an iterative version of it. #card
?
**Recursive Version:**
The function input expects $i$ (next number to print) and $n$.
• **Base case:** when $i>n$ there is nothing left to do and we stop.
• **Non-base case:** for $1\le i\le n$ we print the number $i$ and call the procedure recursively on $i+1$.

```text
Recursive_Print(i, n)
    if i ≥ 1 AND i ≤ n then
        print i
        Recursive_Print(i+1, n)
```

Main call: $\textsf{Recursive_Print(1, n)}$.

**Iterative Version:**

```text
Iterative_Print(n)
    for i := 1 to n do
        print i
```
