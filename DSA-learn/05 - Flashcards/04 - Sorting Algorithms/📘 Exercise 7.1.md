---
title: "📘 Exercise 7.1"
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
  - "📘 Exercise 7.1"
---

# 🎴 📘 Exercise 7.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 7.1

**Input:** A sorted array $A$ of $n$ integers whose values can only be $0$ or $1$.
**Output:** The number of occurrences of $1$ in $A$.

Write the pseudocode of a Divide and Conquer algorithm requiring $O(\log n)$ time in the worst case. Write the recurrence equation and solve it to prove the required time complexity. #card
?
**Reasoning:**
Since $A$ is sorted and contains only 0s and 1s, all 0s precede all 1s. The count of 1s is simply $n - i_{first}$, where $i_{first}$ is the index of the first occurrence of 1. Binary search finds this first occurrence in $O(\log n)$ time.

**Pseudocode:**

```text
Algorithm CountOnes(A, n):
    idx ≤ftarrow FindFirstOne(A, 0, n - 1)
    if idx = -1 then return 0
    return n - idx

Function FindFirstOne(A, low, high):
    if low > high then return -1
    mid ≤ftarrow floor( (low + high) / 2 )
    if A[mid] = 1 then
        if mid = 0 A[mid - 1] = 0 then return mid
        return FindFirstOne(A, low, mid - 1)
    else
        return FindFirstOne(A, mid + 1, high)
```

**Recurrence and Complexity:**
In each step, the algorithm performs $O(1)$ comparisons and recurses on half the array:

```text
T(n) = T(n/2) + O(1), T(1) = O(1)
```

By Case 2 of the Master Theorem ($a = 1, b = 2, f(n) = O(1)$), $n^{\log_2 1} = n^0 = 1$, so $T(n) = \Theta(\log n)$.
