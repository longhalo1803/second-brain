---
title: "📘 Exercise 3.1"
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
  - "📘 Exercise 3.1"
---

# 🎴 📘 Exercise 3.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 3.1

**Input:** A sorted array $A$ of $n$ distinct integers (both positive and negative).
**Output:** Print all pairs of indices $(i, j)$ such that $0 \le i, j \le n - 1$, $i \ne j$, and $A[i] = 3 \cdot A[j]$, or print $(-1, -1)$ if no such pair exists.

- Show an example of input and output containing both positive and negative values.
- Describe an algorithm solving the problem in sub-quadratic time in $n$.
- Provide the pseudocode.
- Analyze the computational complexity. #card
  ?
  **Reasoning:**
  Since $A$ is sorted and distinct, for each index $j$ we can search for the target value $3 \cdot A[j]$ using binary search in $O(\log n)$ time. Repeating this for all $n$ values yields $O(n \log n)$ time, which is strictly sub-quadratic.

**1. Example:**
Input: $A = [-9, -3, -1, 0, 2, 4, 6, 12]$.
Target pairs where $A[i] = 3 \cdot A[j]$ and $i \ne j$:

- $j = 1 \implies A[1] = -3$, target $-9 = A[0] \implies (0, 1)$
- $j = 4 \implies A[4] = 2$, target $6 = A[6] \implies (6, 4)$
- $j = 5 \implies A[5] = 4$, target $12 = A[7] \implies (7, 5)$Output: $(0, 1), (6, 4), (7, 5)$. (Note: for $A[3] = 0$, $i = j = 3$, which is excluded).

**2. Algorithm Description:**
Iterate $j$ from $0$ to $n-1$. Compute $target = 3 \cdot A[j]$. Perform binary search for $target$ in $A$. If found at index $i$ with $i \ne j$, print $(i, j)$ and set a boolean flag to true. If the flag remains false after the loop, print $(-1, -1)$.

**3. Pseudocode:**

```text
Algorithm FindTripledPairs(A, n):
    found ≤ftarrow false
    for j ≤ftarrow 0 to n - 1 do
        target ≤ftarrow 3 A[j]
        i ≤ftarrow BinarySearch(A, 0, n - 1, target)
        if i ≠ -1 i ≠ j then
            print (i, j); \; found ≤ftarrow true
    if not found then print (-1, -1)
```

**4. Complexity:**

- Time Complexity: $n$ iterations, each executing a binary search costing $O(\log n)$, giving $O(n \log n)$.
- Space Complexity: $O(1)$ auxiliary space.
