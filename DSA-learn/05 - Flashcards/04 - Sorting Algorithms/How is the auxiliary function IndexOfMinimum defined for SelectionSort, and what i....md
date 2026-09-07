---
title: "How is the auxiliary function IndexOfMinimum defined for SelectionSort, and what i..."
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
  - "How is the auxiliary function IndexOfMinimum defined for SelectionSort, and what i..."
---

# 🎴 How is the auxiliary function IndexOfMinimum defined for SelectionSort, and what i...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 How is the auxiliary function `IndexOfMinimum` defined for SelectionSort, and what is its cost?

**Input:** Array $A$ of $n$ elements and an index $i$ ($0 \le i \le n-1$).
**Output: **The index of the minimum element in the subsequence $A[i \dots n-1]$. #card
?
**Pseudocode:**

```text
IndexOfMinimum(A, i, n)
    k := i
    for j := i + 1 to n - 1 do
        if A[j] < A[k] then
            k := j
    return k
```

**Computational cost:**
It performs exactly $(n - 1) - (i + 1) + 1 = n - 1 - i$ comparisons between elements of $A$, thus having a time complexity equal to:

$$
\Theta(n - i)
$$
