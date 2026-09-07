---
title: "Prove by induction that the direct recursive computation of L[k] for LIS requires..."
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
  - "Prove by induction that the direct recursive computation of L[k] for LIS requires..."
---

# 🎴 Prove by induction that the direct recursive computation of L[k] for LIS requires...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: Prove by induction that the direct recursive computation of $L[k]$ for LIS requires an exponential number of recursive calls $f(k) = 2^{k-1}$. #card

?
We want to prove that in the worst case (where all previous elements are smaller than $a_k$), the recursive calls needed to compute $L[k]$ are $f(k) = 2^{k-1}$.

- **Base Case ($k = 1$):**
  $f(1) = 2^{1-1} = 2^0 = 1$ (only 1 call, the first node has no predecessors). TRUE.
- **Inductive Hypothesis:**
  For each $j = 1, \dots, k-1$, assume that $f(j) = 2^{j-1}$ recursive calls are required.
- **Inductive Step:**
  To compute $L[k]$ we must make the call for node $k$ itself, plus the recursive calls for all its predecessors $L[1], \dots, L[k-1]$:

$$

f(k) = 1 + \sum*{j=1}^{k-1} f(j) = 1 + \sum*{j=1}^{k-1} 2^{j-1}

$$

Knowing that the sum of powers of 2 is $\sum_{i=0}^{m-1} 2^i = 2^m - 1$:

$$

f(k) = 1 + (2^{k-1} - 1) = 2^{k-1}

$$

**Conclusion:** naive recursion without memoization makes $O(2^n)$ calls because it repeatedly recomputes the exact same subproblems.
