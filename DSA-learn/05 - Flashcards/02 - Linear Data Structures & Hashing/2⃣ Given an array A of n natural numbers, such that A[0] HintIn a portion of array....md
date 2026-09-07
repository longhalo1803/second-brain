---
title: "2⃣ Given an array A of n natural numbers, such that A[0] HintIn a portion of array..."
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
  - "2⃣ Given an array A of n natural numbers, such that A[0] HintIn a portion of array..."
---

# 🎴 2⃣ Given an array A of n natural numbers, such that A[0] HintIn a portion of array...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📝📍2️⃣ Given an array $A$ of $n$ natural numbers, such that $A[0] 💡 HintIn a portion of array $A[i \dots j]$ without jumps, the difference between the last and first element must be exactly equal to the difference of the indices, i.e., $A[j] - A[i] = j - i$. #card

?
⚠️ Warning: "*the index _$i \in \{1, \dots, n-1\}$_ is called a jump if *$A[i-1] + 1 j - i$, then there must exist at least one jump in the interval $[i, j]$.
We exploit this property to apply binary search:
*• *If $A[j] - A[i] = j - i$, there are no jumps in interval $[i, j]$ (we return $-1$).
*• *Calculate middle index $k = \lfloor(i + j) / 2\rfloor$.
*• *Check if $k$ itself is a jump (i.e., if $A[k] > A[k-1] + 1$). In that case, return $k$. _[optimization]_
*• *Otherwise, check if the left half $A[i \dots k]$ contains a jump (that is, if $A[k] - A[i] > k - i$). If yes, recursively search left; otherwise, the jump is necessarily to the right.
The initial call will be FindJump(A, 0, n - 1).

**3. Pseudocode**

```text
FindJump(A, i, j)
    if A[j] - A[i] = j - i then
        return -1
    if j - i = 1 then
        return j
    k := floor((i + j) / 2)
    if A[k] > A[k - 1] + 1 then
        return k
    if A[k] - A[i] > k - i then
        return FindJump(A, i, k)
    else
        return FindJump(A, k, j)
```

📌 Note: the check `if A[k] > A[k-1] + 1 then return k` is an optional optimization (_early exit_) useful when the jump is at the center of the interval.
(Notice that **no** $k-1$ or $k+1$ is done in recursive calls unlike standard binary search: if done, the pair formed by $k$ and its neighbor would be lost. For example, the jump could be right between $k-1$ and $k$, or between $k$ and $k+1$. Keeping $k$ as an endpoint in sub-intervals guarantees that no pair of adjacent elements is excluded, as we are looking for a jump/discontinuity between two adjacent positions, not an exact array value.)
** 4. Complexity**
At each recursive step, the size of the interval is halved. The number of operations per step is $O(1)$. Thus the complexity in the worst case is $O(\log n)$.

📌 Iterative version (still $O(\log n)$):

```text
FindJump(A, n)
    i := 0
    j := n - 1
    while j - i > 1 do
        k := floor((i + j) / 2)
        if A[k] > A[k - 1] + 1 then
            return k
        if A[k] - A[i] > k - i then
            j := k
        else
            i := k
    if A[j] > A[i] + 1 then
        return j
    return {-1}
```
