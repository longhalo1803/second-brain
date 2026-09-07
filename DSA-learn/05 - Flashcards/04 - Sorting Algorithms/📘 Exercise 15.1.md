---
title: "📘 Exercise 15.1"
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
  - "📘 Exercise 15.1"
---

# 🎴 📘 Exercise 15.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 15.1

**Input:** An array $A$ of $n$ real numbers and a real number $x$.
**Output:** TRUE if there exist two distinct elements in $A$ whose sum is $x$, FALSE otherwise.

Write an algorithm with $O(n \log n)$ computational complexity. Explain its functioning and provide pseudocode. #card
?
**Reasoning:**
First sort the array in $O(n \log n)$ time using MergeSort or HeapSort. Then, apply the two-pointer technique starting at opposite ends of the sorted array in $O(n)$ time.

**Algorithm Description:**
Sort $A$ in non-decreasing order. Initialize $left \leftarrow 0$ and $right \leftarrow n - 1$. While $left x$, decrement $right$ to decrease the sum. If pointers meet without finding a pair, return FALSE.

**Pseudocode:**

```text
Algorithm TwoSum(A, n, x):
    MergeSort(A, 0, n - 1)
    left ≤ftarrow 0, \; right ≤ftarrow n - 1
    while left < right do
        current_sum ≤ftarrow A[left] + A[right]
        if current_sum = x then return TRUE
        else if current_sum < x then
            left ≤ftarrow left + 1
        else
            right ≤ftarrow right - 1
    return FALSE
```

**Complexity:**

- Time Complexity: Sorting takes $O(n \log n)$, two-pointer scan takes $O(n)$. Overall time is $O(n \log n)$.
- Space Complexity: $O(n)$ for MergeSort or $O(1)$ if in-place HeapSort is used.
