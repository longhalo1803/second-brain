---
title: "What is the exact maximum number of iterations in the worst case for iterative bin..."
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the exact maximum number of iterations in the worst case for iterative bin..."
---

# 🎴 What is the exact maximum number of iterations in the worst case for iterative bin...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the exact maximum number of iterations in the worst case for iterative binary search $\#it(n)$? #card

?
Let $\#it(n)$ be the number of iterations required in the worst case by binary search on an input of size $n$ to reach the termination condition $i > j$.
The following relation holds:

$$
\boxed{\#it(n) \le \log_2 n + 1}
$$

❓ Why?
In short, because at most $\log_2 n$ **halvings** are needed to reduce the search space to a single element, **plus 1 final iteration** to check that last remaining element.
_Remember_: after $k$ iterations, the size of the remaining subarray is at most:

$$
\left\lfloor \frac{n}{2^k} \right\rfloor \geq 1
$$

($\overset{\cdot 2^k}{\implies} n \ge 2^k \overset{\log_2}{\implies} \log_2 n \ge k \overset{\leftrightarrow}{\implies} k \le \log_2 n$)
