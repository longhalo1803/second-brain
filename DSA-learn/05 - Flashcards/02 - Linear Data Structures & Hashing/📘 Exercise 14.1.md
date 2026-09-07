---
title: "📘 Exercise 14.1"
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "📘 Exercise 14.1"
---

# 🎴 📘 Exercise 14.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📘 Exercise 14.1

Given a strictly increasing array $A$ of $n$ natural numbers ($A[0] < A[1] < \dots < A[n-1]$), an index $i \in \{1, \dots, n-1\}$ is called a _jump_ if $A[i-1] + 1 < A[i]$.

- Show two examples with $n \ge 5$: one without a jump and one with a jump.
- Write an algorithm with $O(\log n)$ computational complexity that returns $-1$ if $A$ has no jump, and returns the index of a jump otherwise. Include brief explanation and pseudocode. #card
  ?
  **Reasoning:**
  If an array has no jump, the elements are strictly consecutive, so $A[high] - A[low] = high - low$. If $A[high] - A[low] > high - low$, there must be at least one jump in the range $[low, high]$. We can divide and conquer via binary search.

**1. Examples:**

- _No jump:_ $A = [2, 3, 4, 5, 6]$ ($n = 5$). Output: $-1$.
- _With jump:_ $A = [2, 3, 6, 7, 8]$. Here $A[1] + 1 = 4 mid - low$, a jump exists in the left half $[low, mid]$. Otherwise, a jump must exist in the right half $[mid, high]$.

**3. Pseudocode:**

```text
Algorithm FindJump(A, n):
    if A[n-1] - A[0] = n - 1 then return -1
    low ≤ftarrow 0, \; high ≤ftarrow n - 1
    while low  mid - low then
            high ≤ftarrow mid
        else
            low ≤ftarrow mid
    return -1
```

**Complexity:**
Time Complexity is $O(\log n)$, space complexity is $O(1)$.
