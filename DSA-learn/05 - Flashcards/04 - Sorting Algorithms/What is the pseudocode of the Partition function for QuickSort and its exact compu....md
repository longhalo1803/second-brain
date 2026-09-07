---
title: "What is the pseudocode of the Partition function for QuickSort and its exact compu..."
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
  - "What is the pseudocode of the Partition function for QuickSort and its exact compu..."
---

# 🎴 What is the pseudocode of the Partition function for QuickSort and its exact compu...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🟢 What is the pseudocode of the `Partition` function for QuickSort and its exact computational cost? #card

?

```text
Partition(A, p, r)
    x := A[r]
    i := p - 1
        for j := p to r-1 do // r-p comparisons
        if A[j] ≤ x then
            i := i + 1
            swap A[i] ≤ftrightarrow A[j]
    swap A[r] ≤ftrightarrow A[i+1]
    return i + 1
```

**Computational cost:**
Executes exactly one comparison in each iteration of the `for` loop, for an exact total of $r - p$ comparisons, thus having a time complexity of $\Theta(n)$ on a subarray of size $n = r - p + 1$.

📌 Note: the `Partition` function is called recursively twice in the main algorithm:

```text
QuickSort(A, p, r)
    if p source).
The optimization of randomly choosing the pivot solves the issue with sorted or reversed data, but it does not resolve performance in any way when all elements are equal.
```
