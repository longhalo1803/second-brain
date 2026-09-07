---
title: "What is the pseudocode of the main recursive procedure of QuickSort"
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
  - "What is the pseudocode of the main recursive procedure of QuickSort"
---

# 🎴 What is the pseudocode of the main recursive procedure of QuickSort

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🟢 What is the pseudocode of the main recursive procedure of QuickSort? #card

?

```text
QuickSort(A, p, r)
    if p < r then
        q := Partition(A, p, r)
        QuickSort(A, p, q-1)
        QuickSort(A, q+1, r)
```

Main call: $\textsf{QuickSort}(A, 0, n-1)$.

📌 Note: the base case is handled implicitly by the condition `if p < r`: if true, the sub-array contains two or more elements, so it partitions the array and recursively sorts the left and right sub-arrays. Otherwise, for sub-arrays of 1 or 0 elements, the function does nothing and returns immediately.
