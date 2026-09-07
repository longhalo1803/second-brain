---
title: "📘 Exercise 12.2"
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
  - "📘 Exercise 12.2"
---

# 🎴 📘 Exercise 12.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 12.2

**Input:** An array $A$ of $n$ distinct natural numbers sorted in increasing order (assume natural numbers start from $0$).
**Output:** The index where the smallest missing natural number should appear, or $-1$ if no number is missing from the prefix.

- Provide an example with $n \ge 8$.
- Describe an algorithm with $O(\log n)$ time complexity and provide pseudocode. #card
  ?
  **Reasoning:**
  In a complete prefix of natural numbers $\{0, 1, 2, \dots\}$, every element satisfies $A[i] = i$. The first missing number causes all subsequent elements to satisfy $A[i] > i$. We can find the first index where $A[i] > i$ using binary search.

**1. Example:**
Input: $A = [0, 1, 2, 3, 5, 6, 7, 8]$ ($n = 8$).
At index $4$, $A[4] = 5 \ne 4$. The smallest missing number is 4, which should be placed at index 4. Output: 4.
If $A = [0, 1, 2, 3, 4, 5, 6, 7]$, no number is missing; output: $-1$.

**2. Algorithm Description:**
Check if $A[n-1] = n - 1$; if so, no element is missing in the range, return $-1$. Otherwise, use binary search on $[0, n - 1]$. At index $mid$, if $A[mid] = mid$, the missing element must be to the right ($low \leftarrow mid + 1$). If $A[mid] > mid$, the first mismatch is either at $mid$ or to the left ($high \leftarrow mid$). When $low = high$, return $low$.

**Pseudocode:**

```text
Algorithm SmallestMissingIndex(A, n):
    if A[n - 1] = n - 1 then return -1
    low ≤ftarrow 0, \; high ≤ftarrow n - 1
    while low < high do
        mid ≤ftarrow floor( (low + high) / 2 )
        if A[mid] = mid then
            low ≤ftarrow mid + 1
        else
            high ≤ftarrow mid
    return low
```

**Complexity:**
Runs in $O(\log n)$ time and $O(1)$ auxiliary space.
