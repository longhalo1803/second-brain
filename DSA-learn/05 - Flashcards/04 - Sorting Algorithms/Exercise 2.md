---
title: "Exercise 2"
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
  - "Exercise 2"
---

# 🎴 Exercise 2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 **Exercise 2**

Previously, a recursive implementation of the SelectionSort sorting algorithm was presented.
Write an iterative implementation (that does not use recursion) and analyze its computational cost. #card
?
We exploit the same function $\textsf{MinimumIndex(A, i, n)}$ seen previously:

```text
SelectionSort(A, n)
    for i := 0 to n - 2 do
        k := MinimumIndex(A, i, n)
        swap A[i] and A[k]
```

**Computational cost analysis:**
The computational cost is studied in exactly the same way as the recursive version. The number of comparisons is given by the summation:

$$
\sum_{i=0}^{n-2}(n-1-i) \in \Theta(n^{2})
$$
