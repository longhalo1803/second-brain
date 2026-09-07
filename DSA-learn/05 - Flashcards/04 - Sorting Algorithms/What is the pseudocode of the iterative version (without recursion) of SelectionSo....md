---
title: "What is the pseudocode of the iterative version (without recursion) of SelectionSo..."
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
  - "What is the pseudocode of the iterative version (without recursion) of SelectionSo..."
---

# 🎴 What is the pseudocode of the iterative version (without recursion) of SelectionSo...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 What is the pseudocode of the iterative version (without recursion) of SelectionSort and what is its complexity? #card

?
**Pseudocode:**

```text
SelectionSort(A, n)
    for i := 0 to n - 2 do
        k := IndexOfMinimum(A, i, n)
        swap A[i] and A[k]
```

**Main call:**
No special recursive call is needed (just pass the array and its size $n$).

**Computational cost:**

$$
T(n) \in \Theta(n^2)
$$

❓ Why loop up to $n-2$?
Because the last element sorts itself, meaning after sorting all other smaller elements (by taking the minimum from the unsorted subarray each time), the single element left is guaranteed to be the largest of all and is therefore already sorted.
