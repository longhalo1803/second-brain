---
title: "What happens in the best case of QuickSort and what is its asymptotic complexity"
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What happens in the best case of QuickSort and what is its asymptotic complexity"
---

# 🎴 What happens in the best case of QuickSort and what is its asymptotic complexity

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What happens in the **best case** of QuickSort and what is its asymptotic complexity? #card

?
The **best case** occurs when the partition is _**perfectly balanced**_ at every level, that is, when the pivot divides the array into two parts of nearly equal size ($q \approx n/2$).

**Recurrence equation:**

$$
T(n) = 2T(n/2) + n - 1
$$

Applying the Master Theorem with $a=2, b=2, d=1$:
Since $\log_b a = \log_2 2 = 1 = d$, we fall into the balanced case:

$$
T(n) \in \Theta(n \log n)
$$

📌 Note:
QuickSort can be recursively perfectly balanced only if $n = 2^k - 1$ for some $k \ge 0$ (although this condition alone does not automatically guarantee perfect balance).

Recursion tree (balanced binary tree):
