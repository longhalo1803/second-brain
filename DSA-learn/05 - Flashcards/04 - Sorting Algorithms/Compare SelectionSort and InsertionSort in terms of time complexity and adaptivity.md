---
title: "Compare SelectionSort and InsertionSort in terms of time complexity and adaptivity"
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
  - "Compare SelectionSort and InsertionSort in terms of time complexity and adaptivity"
---

# 🎴 Compare SelectionSort and InsertionSort in terms of time complexity and adaptivity

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Compare SelectionSort and InsertionSort in terms of time complexity and adaptivity #card

?
AlgorithmBest CaseAverage CaseWorst CaseAdaptive?**SelectionSort**$\Theta(n^2)$$\Theta(n^2)$$\Theta(n^2)$❌ NO (always makes $\frac{n(n-1)}{2}$ comparisons)**InsertionSort**$\Theta(n)$$\Theta(n^2)$$\Theta(n^2)$✅ YES (exploits initial input order)
**Practical considerations:**

- Although both have quadratic complexity $\Theta(n^2)$ in the worst and average cases, **InsertionSort is generally preferred in practice** because for nearly sorted arrays it requires near-linear time $\Theta(n)$.
- Both algorithms sort the array _in-place_ with constant auxiliary space $O(1)$.
