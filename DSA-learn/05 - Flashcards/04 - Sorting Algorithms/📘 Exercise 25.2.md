---
title: "📘 Exercise 25.2"
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
  - "📘 Exercise 25.2"
---

# 🎴 📘 Exercise 25.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 25.2

**Input:** An array $A$ containing $n$ real numbers sorted in non-decreasing order (not necessarily distinct), and two real values $low$ and $up$.
**Output:** The number of elements in $A$ that belong to the closed interval $[low, up]$.

- Show an example with $n \ge 10$.
- Describe an $O(\log n)$ algorithm in words.
- Provide pseudocode.
- Trace execution on the example.
- Discuss correctness and computational complexity. #card
  ?
  **Reasoning:**
  Use binary search twice: once to find the first index $i$ where $A[i] \ge low$, and once to find the last index $j$ where $A[j] \le up$. If both valid indices exist and $i \le j$, the count is $j - i + 1$; otherwise 0.

**1. Example:**
$A = [1.0, 2.5, 3.0, 4.2, 4.2, 5.0, 6.1, 7.8, 8.0, 9.5]$ ($n = 10$). Let $low = 3.0, up = 6.5$.
First element $\ge 3.0$ is at index $2$. Last element $\le 6.5$ is $6.1$ at index $6$. Count: $6 - 2 + 1 = 5$.

**2. Pseudocode:**

```text
Algorithm CountInRange(A, n, low, up):
    if low > up then return 0
    idx_1 ≤ftarrow FindFirstGE(A, 0, n - 1, low)
    if idx_1 = -1 A[idx_1] > up then return 0
    idx_2 ≤ftarrow FindLastLE(A, 0, n - 1, up)
    return idx_2 - idx_1 + 1

Function FindFirstGE(A, l, h, val):
    res ≤ftarrow -1
    while l ≤ h do
        m ≤ftarrow floor( (l + h) / 2 )
        if A[m] ≥ val then res ≤ftarrow m; \; h ≤ftarrow m - 1
        else l ≤ftarrow m + 1
    return res

Function FindLastLE(A, l, h, val):
    res ≤ftarrow -1
    while l ≤ h do
        m ≤ftarrow floor( (l + h) / 2 )
        if A[m] ≤ val then res ≤ftarrow m; \; l ≤ftarrow m + 1
        else h ≤ftarrow m - 1
    return res
```

**Complexity:**
Two binary searches take $2 \times O(\log n) = O(\log n)$ time and $O(1)$ space.
