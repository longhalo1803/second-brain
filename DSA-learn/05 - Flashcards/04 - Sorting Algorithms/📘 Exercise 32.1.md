---
title: "📘 Exercise 32.1"
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
  - "📘 Exercise 32.1"
---

# 🎴 📘 Exercise 32.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 32.1

**Input:** An array $A$ of $n$ integers sorted in non-decreasing order, and an integer $k$.
**Output:** The index of the first element in $A$ that is strictly greater than $k$, or $-1$ if no such element exists.

- Show an example where the index exists.
- Describe an algorithm solving the problem in $O(\log n)$ time.
- Provide the pseudocode.
- Explain why the computational complexity is $O(\log n)$. #card
  ?
  **Reasoning:**
  Since $A$ is sorted, elements $\le k$ occupy a prefix of $A$, while elements $> k$ occupy the remaining suffix. We can perform a binary search for the first index where $A[i] > k$ (equivalent to the standard upper-bound binary search).

**1. Example:**
Input: $A = [1, 3, 3, 5, 7, 8, 10]$, $k = 3$.
The first element strictly greater than $3$ is $5$ at index 3. Output: 3.

**2. Algorithm Description:**
Initialize $low \leftarrow 0$, $high \leftarrow n - 1$, and $ans \leftarrow -1$. At each step, examine $mid = \lfloor (low + high) / 2 \rfloor$. If $A[mid] > k$, it is a candidate answer; record $ans \leftarrow mid$ and search the left sub-array ($high \leftarrow mid - 1$) to see if an earlier element also exceeds $k$. If $A[mid] \le k$, any element $> k$ must be strictly to the right, so set $low \leftarrow mid + 1$. Return $ans$.

**3. Pseudocode:**

```text
Algorithm FirstGreaterThanK(A, n, k):
    low ≤ftarrow 0, \; high ≤ftarrow n - 1
    ans ≤ftarrow -1
    while low ≤ high do
        mid ≤ftarrow floor( (low + high) / 2 )
        if A[mid] > k then
            ans ≤ftarrow mid
            high ≤ftarrow mid - 1
        else
            low ≤ftarrow mid + 1
    return ans
```

**4. Complexity:**
In each iteration of the while-loop, the search space $[low, high]$ is halved using a constant number of operations:

$$

T(n) = T(n/2) + O(1)

$$

By the Master Theorem, the running time is strictly $O(\log n)$. The auxiliary space is $O(1)$.
