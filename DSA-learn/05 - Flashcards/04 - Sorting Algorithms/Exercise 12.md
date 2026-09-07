---
title: "Exercise 12"
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
  - "Exercise 12"
---

# 🎴 Exercise 12

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Exercise 12

Write an alternative version of `Partition` for `QuickSort`.
Given as input the subarray $A[p..r]$, use two cursors initially positioned at the first and last elements of the portion (thus $i=p$ and $j=r$). Choose the first element as the pivot ($A[p]$) and, until the two cursors meet or cross each other, proceed according to the following strategy:

1. advance cursor $i$ to the right until it is positioned on a value strictly greater than the pivot (if one exists);
2. advance cursor $j$ to the left until it is positioned on a value strictly smaller than the pivot (if one exists);
3. swap the values at the cursor positions with each other;
   Finally, place the pivot in the correct position and return its index.

Provide an execution example of this version of `Partition` on a sequence $A$ with at least 10 elements. Analyze the computational cost of this version of `Partition`. #card
?
**Pseudocode:**

```text
PartitionHoareVariant(A, p, r)
    pivot := A[p]
    i := p + 1
    j := r
    while i ≤ j do
        while (i ≤ r AND A[i] ≤ pivot) do
            i := i + 1
        while (j ≥ p+1 AND A[j] ≥ pivot) do
            j := j - 1
        if i  12$); $j$ moves back to pos 9 ($7  12$); $j$ moves back to pos 7 ($1  12$); $j$ moves back to pos 5 ($9  j$ ($6 > 5$), the loop terminates.
- Swap pivot $A[0]=12$ with $A[5]=9$.
- Final array: $\langle 9, 5, 7, 3, 1, 12, 15, 22, 14, 18 \rangle$, returned pivot index: $j=5$.
**Computational cost:**
The cursors $i$ and $j$ advance/retreat examining each element at most once. The total number of comparisons and increments is proportional to the number of elements in the subarray $r - p + 1 = n$. The time complexity is therefore **$\Theta(n)$**.
```
