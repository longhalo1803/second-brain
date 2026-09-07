---
title: "How does the randomized version of QuickSort work and what is it used for"
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
  - "How does the randomized version of QuickSort work and what is it used for"
---

# 🎴 How does the randomized version of QuickSort work and what is it used for

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How does the randomized version of QuickSort work and what is it used for? #card

?
To avoid the worst case $\Theta(n^2)$ caused by specific inputs (e.g. already sorted arrays), the pivot is chosen randomly.

```text
Randomized-Partition(A, p, r)
    i := Random(p, r)
    swap A[i] ≤ftrightarrow A[r]
    return Partition(A, p, r)
```

````text
Randomized-QuickSort(A, p, r)
    if p 📝 Worst-case example for non-randomized QS version

If the last element is always chosen as the pivot ($A[r]$) and the array is already sorted in ascending order, for example $A = [1, 2, 3, 4, 5]$:

```text
Partition(A, 1, 5) pivot = 5 subarrays: [1, 2, 3, 4] and []
Partition(A, 1, 4) pivot = 4 subarrays: [1, 2, 3] and []
Partition(A, 1, 3) pivot = 3 subarrays: [1, 2] and []
````

At each step one subarray remains empty and the other decreases by only one element (it does not halve the size of the subproblems at all, it drops by just one element at a time). The recursion tree becomes completely unbalanced, reaching a height of $n$, with a total number of comparisons equal to:

$$
\sum_{k=1}^{n-1} k = \frac{n(n-1)}{2} = \Theta(n^2)
$$

In contrast, with the randomized version, on the same sorted array $A = [1, 2, 3, 4, 5]$, the pivot is chosen randomly at each call. If, for example, the median value $3$ is drawn:

```text
Randomized-Partition(A, 1, 5) pivot = 3 subarrays: [1, 2] and [4, 5]
```

The array is divided in half in a balanced way. Even in worst-case input scenarios, the probability of always picking the worst pivot at every level is negligible, guaranteeing a time of $\Theta(n \log n)$.
