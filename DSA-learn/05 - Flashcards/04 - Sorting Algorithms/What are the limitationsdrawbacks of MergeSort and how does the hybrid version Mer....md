---
title: "What are the limitationsdrawbacks of MergeSort and how does the hybrid version Mer..."
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
  - "What are the limitationsdrawbacks of MergeSort and how does the hybrid version Mer..."
---

# 🎴 What are the limitationsdrawbacks of MergeSort and how does the hybrid version Mer...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the limitations/drawbacks of MergeSort and how does the hybrid version MergeSort + Insertion Sort work? #card

?
**Drawbacks and practical limitations of MergeSort:**

- **Use of extra space:** it is not an _in-place_ algorithm; it requires auxiliary memory $O(n)$ to allocate supporting arrays during merging.
- **Recursion overhead:** for very small sub-arrays (e.g., of size $\le 10-15$), the fixed cost of recursive calls and stack management exceeds the execution time of simple algorithms like **Insertion Sort**.
  **Hybridization MergeSort + Insertion Sort:**
  A threshold constant $s > 1$ is set. When the size of the sub-array to be sorted becomes $\le s$, recursion is stopped and **Insertion Sort** is used to sort that small block directly.

**Pseudocode of the hybrid algorithm:**

```text
Hybrid_MergeSort(A, i, j, s)
    k := floor((i + j) / 2)
    if (k - i + 1 ≤ s) then              // Left half below threshold?
        InsertionSort(A, i, k)               // Use Insertion Sort
    else
        Hybrid_MergeSort(A, i, k, s)         // Continue with MergeSort
    if (j - k ≤ s) then                  // Right half below threshold?
        InsertionSort(A, k + 1, j)           // Use Insertion Sort
    else
        Hybrid_MergeSort(A, k + 1, j, s)     // Continue with MergeSort
    Merge(A, i, k, j)                    // Merges the two sorted portions
```

📌 Note: `InsertionSort(A, left, right)` is an adapted version of Insertion Sort that operates exclusively on the sub-array bounded between indices `left` and `right` (inclusive).
