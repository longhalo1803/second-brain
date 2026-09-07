---
title: "📘 Exercise 1.1"
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
  - "📘 Exercise 1.1"
---

# 🎴 📘 Exercise 1.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 1.1

**Input:** An array $A$ of $n$ integers sorted in non-decreasing order, where each element $A[i] \in \{1, 2, \dots, n-1\}$ for every $i = 0, 1, \dots, n-1$, such that all elements are distinct except for exactly one duplicate pair.
**Output:** The unique integer $k \in \{1, 2, \dots, n-1\}$ that appears twice in $A$.

- Show an example of input and corresponding output with an array of 10 elements.
- Describe an algorithm with $O(\log n)$ computational complexity to solve the problem.
- Write the pseudocode of the described algorithm.
- If $A[i] \in \{1, 2, \dots, n-2\}$ for all $i$, and there were exactly two distinct numbers $k_1 \neq k_2$ appearing twice, how could the algorithm be modified to find the larger between $k_1$ and $k_2$ in $O(\log n)$ time? Describe the solution in words without pseudocode. #card
  ?
  **Reasoning:**
  In an ideal array with no duplicates, $A[i] = i + 1$. Before the first duplicate, $A[i] = i + 1$. From the second occurrence of the duplicate onwards, the values shift such that $A[i] = i$. Therefore, we can perform a binary search to find the duplicate by inspecting whether the equality $A[mid] = mid + 1$ holds.

**1. Example:**
Input: $A = [1, 2, 3, 4, 4, 5, 6, 7, 8, 9]$ ($n = 10$).
Output: $4$.

**2. Algorithm Description:**
Perform binary search over indices $0 \dots n - 1$. At index $mid$, check if $A[mid] = A[mid - 1]$ or $A[mid] = A[mid + 1]$; if so, return $A[mid]$. Otherwise, if $A[mid] = mid + 1$, the duplicate lies strictly to the right, so search in $[mid + 1, high]$. If $A[mid] \le mid$, the duplicate has already occurred to the left, so search in $[low, mid - 1]$.

**3. Pseudocode:**

```text
Algorithm FindDuplicate(A, n):
    low ≤ftarrow 0, \; high ≤ftarrow n - 1
    while low ≤ high do
        mid ≤ftarrow floor( (low + high) / 2 )
        if (mid > 0 A[mid] = A[mid-1]) (mid < n-1 A[mid] = A[mid+1]) then
            return A[mid]
        if A[mid] = mid + 1 then
            low ≤ftarrow mid + 1
        else
            high ≤ftarrow mid - 1
    return -1
```

**4. Two Duplicates Extension:**
With two duplicate values $k_1 < k_2$, the array values satisfy $A[i] = i + 1$ before $k_1$, $A[i] = i$ between $k_1$ and $k_2$, and $A[i] = i - 1$ after $k_2$. To find $\max(k_1, k_2) = k_2$, binary search for the transition where $A[i]$ shifts from $i$ to $i - 1$. If at index $mid$ we have $A[mid] = mid - 1$, the second duplicate has already occurred, so we search the left half. If $A[mid] \ge mid$, the second duplicate lies strictly to the right. This maintains $O(\log n)$ time.
