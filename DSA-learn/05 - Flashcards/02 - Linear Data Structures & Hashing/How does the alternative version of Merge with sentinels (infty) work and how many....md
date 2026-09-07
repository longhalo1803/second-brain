---
title: "How does the alternative version of Merge with sentinels (infty) work and how many..."
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
  - "How does the alternative version of Merge with sentinels (infty) work and how many..."
---

# 🎴 How does the alternative version of Merge with sentinels (infty) work and how many...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 🟢 How does the alternative version of Merge with sentinels ($\infty$) work and how many comparisons does it perform? #card

?
Instead of using a single auxiliary array $B$ and handling the remaining elements separately, two temporary arrays $L$ and $R$ are created by inserting a **sentinel value $\infty$** at the end of each (a value strictly greater than any element in the array).

**Pseudocode ****Alternative Merge with sentinels****:**

```text
Merge_ALT(A, i, k, j)
    n1 := k - i + 1
    n2 := j - k
    create L[0..n1] and R[0..n2]
    for t := 0 to n1 - 1 do              // Copy 1st half of A into L
        L[t] := A[i + t]
    for t := 0 to n2 - 1 do              // Copy 2nd half of A into R
        R[t] := A[k + 1 + t]
    [#f7b37d]{L[n1] := ∈fty}             // Sentinel insertion
    [#f7b37d]{R[n2] := ∈fty}
    l := 0
    r := 0
    for t := i to j do                   // j-i+1 iterations
        if L[l] ≤ R[r] then
            A[t] := L[l]
            l := l + 1
        else
            A[t] := R[r]
            r := r + 1
```

📌 Note: when the algorithm creates $\textsf{L[0}..\textsf{n1]}$ and $\textsf{R[0}..\textsf{n2]}$ it is allocating arrays of length $\textsf{n1 + 1}$ and $\textsf{n2 + 1}$ (since they go from index $\texttt{0}$ up to index $\textsf{n1}$ included) and the copying loops do not fill the last element, which is reserved for sentinels.
📝 Example:

**Advantages and number of comparisons:**

- **Elimination of end-of-array checks:** the sentinel $\infty$ guarantees that an exhausted portion will never win any comparison again, avoiding the need to check if `l` or `r` have gone out of bounds.
- **Fixed number of comparisons:** the `for` loop always executes for exactly $t$ from $i$ to $j$, i.e., for $j - i + 1$ iterations. Therefore, the number of comparisons is **exactly **$j - i + 1$** for every input instance** (both in the best and worst case). In other words, the $\infty$ will never be copied back into A after the merge, because the last loop $\texttt{for } \textsf{t := i} \texttt{ to } \textsf{j} \texttt{ do}$ performs exactly as many iterations as there are numbers in L and R combined, i.e., $j-i+1$, excluding the two sentinels.
