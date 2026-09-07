---
title: "📘 Exercise 6.1"
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
  - "📘 Exercise 6.1"
---

# 🎴 📘 Exercise 6.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 6.1

**Input:** An array $A$ of $n$ integers sorted in non-decreasing order (duplicates may be present) and an integer $x$.
**Output:** The index of the last (rightmost) occurrence of $x$ in $A$, or $-1$ if $x$ is not present.

Design a Divide and Conquer algorithm to solve the problem:

- Describe the algorithm in words specifying Divide, Conquer, and Combine steps.
- Show an example with at least 7 values where $x$ is repeated multiple times.
- Write the pseudocode.
- Analyze the computational complexity. #card
  ?
  **Reasoning:**
  Binary search is a classic Divide and Conquer technique. When $A[mid] = x$, we cannot stop immediately; instead, we check if $mid$ is the rightmost occurrence ($mid = n - 1$ or $A[mid+1] > x$). If not, the rightmost occurrence must lie in the right sub-array.

**1. Divide, Conquer, Combine:**

- _Divide:_ Compute $mid = \lfloor (low + high) / 2 \rfloor$.
- _Conquer:_ If $A[mid] = x$ and ($mid = high \lor A[mid+1] > x$), the answer is $mid$. If $A[mid] \le x$, recurse on the right half $[mid + 1, high]$. If $A[mid] > x$, recurse on the left half $[low, mid - 1]$.
- _Combine:_ Return the index found by the subproblem.
  **2. Example:**
  Input: $A = [1, 3, 5, 5, 5, 8, 10]$, $x = 5$.
  Initial range $[0, 6]$, $mid = 3$, $A[3] = 5$. Since $A[4] = 5$, search right $[4, 6]$. Next $mid = 5$, $A[5] = 8 > 5$, search left $[4, 4]$. At $mid = 4$, $A[4] = 5$ and $A[5] = 8 > 5$. Output: 4.

**3. Pseudocode:**

```text
Algorithm LastOccurrence(A, low, high, x):
    if low > high then return -1
    mid ≤ftarrow floor( (low + high) / 2 )
    if A[mid] = x then
        if mid = high A[mid+1] > x then return mid
        return LastOccurrence(A, mid + 1, high, x)
    if A[mid] < x then
        return LastOccurrence(A, mid + 1, high, x)
    else
        return LastOccurrence(A, low, mid - 1, x)
```

**4. Complexity:**
Recurrence: $T(n) = T(n/2) + O(1)$. By the Master Theorem, $T(n) = O(\log n)$.
