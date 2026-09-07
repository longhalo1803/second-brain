---
title: "What is the pseudocode of the recursive version of SelectionSort and how is it cal..."
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
  - "What is the pseudocode of the recursive version of SelectionSort and how is it cal..."
---

# 🎴 What is the pseudocode of the recursive version of SelectionSort and how is it cal...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🟢 \*What is the pseudocode of the recursive version of SelectionSort and how is it called (main call)? #card

?
**Pseudocode:**

```text
SelectionSort(A, i, n)
    if i < n - 1 then
        k := IndexOfMinimum(A, i, n)
        swap A[i] and A[k]
        SelectionSort(A, i + 1, n)
```

**Main call:**

```text
SelectionSort(A, 0, n)
```

📌 Note:
It is a **procedure** that works _in-place_ (directly modifies the array $A$). At the end of execution, the elements of $A$ are sorted in non-decreasing order.
