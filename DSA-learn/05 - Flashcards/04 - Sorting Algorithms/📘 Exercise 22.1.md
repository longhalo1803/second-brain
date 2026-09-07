---
title: "📘 Exercise 22.1"
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
  - "📘 Exercise 22.1"
---

# 🎴 📘 Exercise 22.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 22.1

**Input:** An array $A$ containing $n$ distinct integers sorted in increasing order.
**Output:** An index $i$ such that $A[i] = i$, or $-1$ if no such index exists.

- Provide an example where such an index exists and one where it does not.
- Provide pseudocode of an $O(\log n)$ algorithm.
- Justify the algorithmic strategy. #card
  ?
  **Reasoning:**
  Define $D[i] = A[i] - i$. Because the elements in $A$ are distinct and sorted, $A[i+1] \ge A[i] + 1$, which implies $A[i+1] - (i+1) \ge A[i] - i$. Hence $D[i]$ is monotonically non-decreasing. Finding $A[i] = i$ is equivalent to finding a root of $D[i] = 0$ via binary search.

**1. Example:**

- Exists: $A = [-3, -1, 2, 5, 7]$. At $i = 2$, $A[2] = 2$. Output: 2.
- Does not exist: $A = [1, 2, 3, 4, 5]$. Output: $-1$.
  **2. Pseudocode:**

```text
Algorithm FindFixedPoint(A, n):
    low ≤ftarrow 0, \; high ≤ftarrow n - 1
    while low ≤ high do
        mid ≤ftarrow floor( (low + high) / 2 )
        if A[mid] = mid then return mid
        else if A[mid] > mid then
            high ≤ftarrow mid - 1
        else
            low ≤ftarrow mid + 1
    return -1
```

**3. Complexity:**
Halves the search space at each step: $O(\log n)$ time and $O(1)$ space.
