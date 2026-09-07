---
title: "Exercise 3.1"
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
  - "Exercise 3.1"
---

# 🎴 Exercise 3.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: 📝 **Exercise 3.1**

Given two positive integers $a$ and $n$, we define $a^{n}=a\cdot a\cdot...\cdot a$ for $n$ times.
Write an iterative algorithm that computes $a^n$ with computational cost $\Theta(n)$. #card
?
Iterative version for computing $a^n$ through successive multiplications:

```text
SlowPower(a, n)
    x := a
    for i := 2 to n do
        x := x a
    return x
```
