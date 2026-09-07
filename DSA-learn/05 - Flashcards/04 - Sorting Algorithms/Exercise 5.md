---
title: "Exercise 5"
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
  - "Exercise 5"
---

# 🎴 Exercise 5

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Exercise 5

Write the pseudocode for a variant of `MergeSort` in which, in addition to array $A$ and $\enclose{horizontalstrike} n$ and indices $i$ and $j$, an integer $s$ is also given as input such that $s \le n$ and $s \in O(1)$.
The sorting algorithm works like MergeSort with the difference that, to reduce the number of recursive calls, subsequences of $A$ of size $\le s$ are sorted by invoking `InsertionSort`. #card
?
Suppose we have a variant of InsertionSort available that, instead of sorting an entire array, sorts a portion of the array between two indices given as input.
Since the idea is to limit the number of recursive calls, before each call we check whether the portion to recurse on is smaller or larger than $s$.
Therefore, we calculate the length of the left subsequence and, only if it is greater than $s$, we invoke the recursive call, otherwise we invoke InsertionSort. We proceed similarly for the right subsequence.

**Main call:** $\textsf{MergeSort(A, 0, n-1, s)}$

**Pseudocode (version 1):**

```text
MergeSort(A, i, j, s)
    k := floor( (i + j) / 2 )
    if (k - i + 1) ≤ s then
        InsertionSort(A, i, k)               // sorts A[i..k] with InsertionSort
    else
        MergeSort(A, i, k, s)
    if (j - k) ≤ s then
        InsertionSort(A, k+1, j)             // sorts A[k+1..j] with InsertionSort
    else
        MergeSort(A, k+1, j, s)
    Merge(A, i, k, j)
```

📌 Note: calls to `InsertionSort` are the _base cases_ of the `MergeSort` recursion.
**Alternative:** the (legitimate) alternative of checking at the beginning of the recursive call whether we are working on a sequence of length less than or equal to $s$ and, in that case, calling `InsertionSort`, leads to (approximately) unnecessarily doubling the number of recursive calls*.
*Recall that, in practice, recursive calls are expensive in terms of time because they involve a context switch requiring the environment (i.e., variable values) of the calling procedure to be saved, which must then be restored upon returning from the recursive call.

**Pseudocode (version 2):**

```text
MergeSort(A, i, j, s)
    if j - i + 1 ≤ s then
        InsertionSort(A, i, j)               // sorts A[i..j] with InsertionSort
    else
        k := floor( (i + j) / 2 )
        MergeSort(A, i, k, s)
        MergeSort(A, k+1, j, s)
        Merge(A, i, k, j)
```

Checking by hand on a small case (e.g., $n=8$, $s=1$):

- Version 1: 7 calls to `MergeSort` + 8 to `InsertionSort`

- Version 2: 15 calls to `MergeSort` + 8 to `InsertionSort`Or look at the case related to exercise 6:

- If we check the length of the subsequence first, we will execute a total of 15 recursive calls to `MergeSort` plus 8 calls to `InsertionSort`.
- If, instead, we check the length at the beginning of the recursive call, we will have a total of 31 recursive calls to `MergeSort` plus 16 calls to `InsertionSort`.We cannot do anything about the number of calls to `InsertionSort`, but we can eliminate 16 useless calls to `MergeSort`.

Summary note:

- In the **optimized version** (_checking the two halves separately before recursing_):
  Before performing recursion, the algorithm checks whether the child halves have size $\le s$. If yes, it directly invokes `InsertionSort` without making the recursive call to `MergeSort`. In other words, when a block is already small enough (≤ s), the parent function directly calls InsertionSort without ever invoking `MergeSort` on that block.
- Calls to `MergeSort` performed **only on internal nodes** → $I$ calls.
- In the **second version** (_checking at the beginning of the call_):
  The algorithm performs the recursive call to `MergeSort` for all subintervals. Once inside the function, it checks whether the size is $\le s$ to decide whether to call `InsertionSort`. In other words, even for a tiny block, `MergeSort` is still called, and only inside that call does it discover the length is ≤ s and delegate to `InsertionSort`.
- Calls to `MergeSort` performed **on both internal nodes and leaves** $\rightarrow I + L \approx 2I$ calls.From the perspective of asymptotic complexity in Big-O notation, the two versions are identical, since O(2⋅N/s)=O(N/s).However, from a practical standpoint (memory overhead and stack management), avoiding L useless function calls is a useful optimization.
