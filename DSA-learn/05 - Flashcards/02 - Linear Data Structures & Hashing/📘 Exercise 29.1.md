---
title: "📘 Exercise 29.1"
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
  - "📘 Exercise 29.1"
---

# 🎴 📘 Exercise 29.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📘 Exercise 29.1

**Input:** An array $A$ of $n$ positive integers where exactly one value appears once, and all other values appear exactly twice in consecutive positions.
**Output:** The index of the unique value.

- Show an example with at least 10 values.
- Describe an $O(\log n)$ algorithm in words, arguing correctness.
- Provide pseudocode.
- Trace execution on the example. #card
  ?
  **Reasoning:**
  Before the single element, pairs start at even indices and end at odd indices ($A[2k] = A[2k+1]$). After the single element, this parity is disrupted, and pairs start at odd indices ($A[2k+1] = A[2k+2]$). Binary search can locate this disruption in $O(\log n)$.

**1. Example ($n = 11$):**
$A = [2, 2, 5, 5, 8, 8, 9, 11, 11, 14, 14]$. Unique value is $9$ at index 6.

**2. Algorithm Description:**
Search on $[0, n - 1]$. At $mid$, ensure $mid$ is even (if odd, decrement by 1). If $A[mid] = A[mid + 1]$, the pair is intact, so the unique element lies to the right: search $[mid + 2, high]$. If $A[mid] \ne A[mid + 1]$, the disruption is at $mid$ or to the left: search $[low, mid]$. When $low = high$, return $low$.

**3. Pseudocode:**

```text
Algorithm FindSingleElement(A, n):
    low ≤ftarrow 0, \; high ≤ftarrow n - 1
    while low < high do
        mid ≤ftarrow floor( (low + high) / 2 )
        if mid 2 = 1 then mid ≤ftarrow mid - 1
        if A[mid] = A[mid + 1] then
            low ≤ftarrow mid + 2
        else
            high ≤ftarrow mid
    return low
```

**Complexity:**
$O(\log n)$ time and $O(1)$ auxiliary space.
