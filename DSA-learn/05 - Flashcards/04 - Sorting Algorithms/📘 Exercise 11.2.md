---
title: "📘 Exercise 11.2"
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
  - "📘 Exercise 11.2"
---

# 🎴 📘 Exercise 11.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 11.2

**Input:** An array $A$ of $n$ integers.
**Output:** Modify $A$ in-place such that all negative values appear to the left of all non-negative values (zero and positive), in $O(n)$ time and $O(1)$ auxiliary space.

- Describe the algorithm and provide pseudocode.
- Show an execution trace on an array of size $n \ge 8$ with mixed values, listing the array state after each swap. #card
  ?
  **Reasoning:**
  We can use a two-pointer partitioning approach (similar to Hoare's partition in QuickSort). One pointer advances from the left looking for non-negative values, while the other advances from the right looking for negative values; when found, they are swapped.

**1. Algorithm Description:**
Initialize pointer $i \leftarrow 0$ and pointer $j \leftarrow n - 1$. While $i < j$, advance $i$ as long as $A[i] < 0$, and decrement $j$ as long as $A[j] \ge 0$. If $i < j$, swap $A[i]$ and $A[j]$, then advance $i$ and decrement $j$. Terminate when $i \ge j$.

**Pseudocode:**

```text
Algorithm PartitionNegatives(A, n):
    i ≤ftarrow 0, \; j ≤ftarrow n - 1
    while i < j do
        while i < j A[i] < 0 do i ≤ftarrow i + 1
        while i < j A[j] ≥ 0 do j ≤ftarrow j - 1
        if i < j then
            swap(A[i], A[j])
            i ≤ftarrow i + 1; \; j ≤ftarrow j - 1
```

**2. Execution Trace ($n = 8$):**
Initial: $A = [4, -2, 7, -5, 0, -1, 3, -8]$

- $i=0$ ($4$), $j=7$ ($-8$): swap $\implies [-8, -2, 7, -5, 0, -1, 3, 4]$
- $i=2$ ($7$), $j=5$ ($-1$): swap $\implies [-8, -2, -1, -5, 0, 7, 3, 4]$
- $i=4$ ($0$), $j=3$ ($-5$): indices cross ($i \ge j$), terminate.Final array: $[-8, -2, -1, -5, 0, 7, 3, 4]$, all negatives appear before non-negatives.
