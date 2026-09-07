---
title: "📘 Exercise 19.2"
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
  - "📘 Exercise 19.2"
---

# 🎴 📘 Exercise 19.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 19.2

An array $A$ of $n$ distinct integers was originally sorted in increasing order, but two distinct elements were swapped.

- Provide pseudocode of an $O(n)$ algorithm to identify the indices $i$ and $j$ of the swapped elements.
- Given the index $i$ of one swapped element, describe an $O(\log n)$ algorithm to find the index $j$ of the other swapped element using binary search, and provide pseudocode. #card
  ?
  **Reasoning:**
  In a sorted array where two elements are swapped, there will be either one or two inversion points where $A[k] > A[k+1]$. If there are two inversions $k_1$ and $k_2$, the swapped indices are $k_1$ and $k_2 + 1$. If there is only one inversion $k_1$, the swapped elements were adjacent ($k_1$ and $k_1 + 1$). When one index $i$ is known, the other index $j$ can be located via binary search by finding where $A[i]$ belongs.

**Pseudocode:**

```text
Algorithm FindSwappedPairLinear(A, n):
    first ≤ftarrow -1, \; second ≤ftarrow -1
    for k ≤ftarrow 0 to n - 2 do
        if A[k] > A[k+1] then
            if first = -1 then first ≤ftarrow k; \; second ≤ftarrow k + 1
            else second ≤ftarrow k + 1
    return (first, second)

Algorithm FindOtherIndexLogN(A, n, i):
    val ≤ftarrow A[i]
    if (i > 0 val < A[i-1]) then
        // val was moved left, so its original position j was to the right
        return BinarySearchRight(A, i + 1, n - 1, val)
    else
        // val was moved right, original position j was to the left
        return BinarySearchLeft(A, 0, i - 1, val)
```

**Complexity:**
Part 1 takes $\Theta(n)$ time and $O(1)$ space. Part 2 takes $O(\log n)$ time via binary search.
