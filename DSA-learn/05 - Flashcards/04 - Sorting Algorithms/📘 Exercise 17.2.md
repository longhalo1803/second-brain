---
title: "📘 Exercise 17.2"
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
  - "📘 Exercise 17.2"
---

# 🎴 📘 Exercise 17.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 17.2

**Input:** An array $A$ of $n$ integers where each value is only $0, 1,$ or $2$.
**Output:** Sort $A$ in non-decreasing order in-place in linear time $O(n)$, subject to:

- The algorithm can ONLY swap elements of the array.
- The algorithm CANNOT use frequency counters or auxiliary arrays.Provide the pseudocode and explain its correctness. #card
  ?
  **Reasoning:**
  This is the classic Dutch National Flag problem. We maintain three pointers dividing the array into four regions: 0s, 1s, unexamined, and 2s.

**Algorithm Description:**
Maintain pointers $low \leftarrow 0$, $mid \leftarrow 0$, and $high \leftarrow n - 1$. Invariants: elements in $A[0 \dots low-1]$ are 0, elements in $A[low \dots mid-1]$ are 1, elements in $A[high+1 \dots n-1]$ are 2. While $mid \le high$:

- If $A[mid] = 0$: swap $A[low]$ and $A[mid]$, increment $low$ and $mid$.
- If $A[mid] = 1$: increment $mid$.
- If $A[mid] = 2$: swap $A[mid]$ and $A[high]$, decrement $high$.
  **Pseudocode:**

```text
Algorithm Sort012(A, n):
    low ≤ftarrow 0, \; mid ≤ftarrow 0, \; high ≤ftarrow n - 1
    while mid ≤ high do
        if A[mid] = 0 then
            swap(A[low], A[mid])
            low ≤ftarrow low + 1; \; mid ≤ftarrow mid + 1
        else if A[mid] = 1 then
            mid ≤ftarrow mid + 1
        else
            swap(A[mid], A[high])
            high ≤ftarrow high - 1
```

**Complexity:**
Every step increments $mid$ or decrements $high$. Exactly at most $n$ iterations occur: $\Theta(n)$ time, $O(1)$ auxiliary space, and strictly uses only swaps.
