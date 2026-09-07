---
title: "What happens in the worst case of QuickSort and what is its asymptotic complexity"
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
  - "What happens in the worst case of QuickSort and what is its asymptotic complexity"
---

# 🎴 What happens in the worst case of QuickSort and what is its asymptotic complexity

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What happens in the **worst case** of QuickSort and what is its asymptotic complexity? #card

?
The **worst case** occurs when the partitioning is _**completely unbalanced**_ at every level of recursion, that is, when the partition produces one subarray with $n-1$ elements and the other with $0$ elements ($q = n-1$ or $q = 0$).

This happens, for instance, if the array is already sorted (or reverse-sorted) and the last element is always chosen as the pivot.

**Recurrence equation: **$T(n) = T(n-1) + n - 1$

**Sum expansion: **$T(n) = (n-1) + (n-2) + \dots + 1 \in \Theta(n^2)$

Recursion tree:
