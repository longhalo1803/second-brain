---
title: "What is the pseudocode of the standard Merge procedure and how many comparisons do..."
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
  - "What is the pseudocode of the standard Merge procedure and how many comparisons do..."
---

# 🎴 What is the pseudocode of the standard Merge procedure and how many comparisons do...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🟢 What is the pseudocode of the standard Merge procedure and how many comparisons does it perform in the worst case to fill B? #card

?
**Pseudocode of `Merge(A, i, k, j)` (version with array B):**

```text
Merge(A, i, k, j)
    l := i                               // Initialize indices
    r := k + 1
    t := 0
    B[0..j-i] new array
    while (l ≤ k AND r ≤ j) do           // Comparisons and filling B
        if A[l] ≤ A[r] then
            B[t] := A[l]
            l := l + 1
        else
            B[t] := A[r]
            r := r + 1
        t := t + 1
    for h := k downto l do               // Copy remaining left elements to the end
        A[j] := A[h]
        j := j - 1
    for h := 0 to t - 1 do               // Copy B back into A
        A[i + h] := B[h]
```

_The algorithm first fills B with the smaller front element of each half. Then it moves any remaining elements of the left half to the end and copies B back into A._
❓ Why are only the remaining elements of the left subarray copied to the end and not those of the right?
There is no need to copy the remaining elements of the right part because they are already in their exact final position in $A$. Why?
The `while` loop ends as soon as one of the two halves finishes:
• **Case A - Left part finishes first** ($l > k$) → all unprocessed remaining elements belong to the right part. Since the right part was already internally sorted and **all its remaining elements are greater than those inserted into **$B$, those on the right already occupy the highest final positions in array $A$. There is no need to touch them.
• **Case B - Right part finishes first** ($r > j$) → there are still elements of the left part to be placed. Those are not in the right place (they occupy central/initial positions).
So the first for loop ($\texttt{for } \textsf{h := k} \texttt{ downto } \texttt{l} \texttt{ do}$) takes these left remaining elements and moves them to the end of the range (into the last positions $A[j]$), freeing up space at the beginning.

**Analysis of the number of comparisons in the `while` loop:**
In the worst case, the procedure performs at most $j - i$** comparisons**.

Proof:

- In each iteration of the `while` loop, exactly **1 comparison** is performed and only one index advances between `l` and `r`.
- The index `l` can advance from $i$ to $k$, taking at most $k - i$ steps.
- The index `r` can advance from $k+1$ to $j$, taking at most $j - (k + 1)$ steps.
- The maximum number of iterations occurs when both reach the end of their respective partitions and a single extra step causes one of the two indices to exit the loop:

$$
\text{Total steps} = (k - i) + (j - k - 1) + 1 = j - i
$$
