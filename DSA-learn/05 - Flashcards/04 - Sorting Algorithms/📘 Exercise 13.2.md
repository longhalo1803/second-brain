---
title: "📘 Exercise 13.2"
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
  - "📘 Exercise 13.2"
---

# 🎴 📘 Exercise 13.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 13.2

**Input:** Two arrays $A$ and $B$, both of known size $n$, storing positive integers, and a known maximum value $k$ such that all elements are $\le k \le n$.
**Output:** TRUE if $A$ and $B$ store the same multiset of natural numbers with identical frequencies, FALSE otherwise.

Provide the pseudocode of an algorithm with LINEAR computational complexity. #card
?
**Reasoning:**
Since the values are bounded by $k \le n$, we can use a frequency counting array of size $k + 1$ in $O(n)$ time without sorting.

**Algorithm Description:**
Allocate a count array $C[1 \dots k]$ initialized to 0. Traverse $A$, incrementing $C[A[i]]$. Traverse $B$, decrementing $C[B[i]]$. Finally, check if all entries in $C$ are 0. If any entry is non-zero, return FALSE; otherwise, return TRUE.

**Pseudocode:**

```text
Algorithm EqualMultisets(A, B, n, k):
    C[] ≤ftarrow array of size k + 1 initialized to 0
    for i ≤ftarrow 0 to n - 1 do
        C[A[i]] ≤ftarrow C[A[i]] + 1
        C[B[i]] ≤ftarrow C[B[i]] - 1
    for v ≤ftarrow 1 to k do
        if C[v] ≠ 0 then return FALSE
    return TRUE
```

**Complexity:**

- Time Complexity: $\Theta(n + k)$. Since $k \le n$, the overall time is $\Theta(n)$ (linear).
- Space Complexity: $\Theta(k) = O(n)$ auxiliary space.
