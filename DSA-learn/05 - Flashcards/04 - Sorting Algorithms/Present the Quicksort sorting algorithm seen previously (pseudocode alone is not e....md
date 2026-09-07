---
title: "Present the Quicksort sorting algorithm seen previously (pseudocode alone is not e..."
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
  - "Present the Quicksort sorting algorithm seen previously (pseudocode alone is not e..."
---

# 🎴 Present the Quicksort sorting algorithm seen previously (pseudocode alone is not e...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Present the Quicksort sorting algorithm seen previously (pseudocode alone is not enough, and is not strictly necessary if the verbal explanation is comprehensive) and analyze its computational cost. #card

?

- **Operation of the Quicksort Algorithm:**
  Quicksort is a sorting algorithm based on the **Divide and Conquer** paradigm:
- **Divide:** Choose an element of the array called the **pivot** (e.g., the last element). Partition the array $A[p \dots r]$ by rearranging elements so that all values less than or equal to the pivot are on its left and all greater values are on its right. The pivot is placed at its final index $q$.
- **Conquer:** Recursively apply Quicksort to both subarrays: the left subarray $A[p \dots q-1]$ and the right subarray $A[q+1 \dots r]$.
- **Combine:** No operation is required: the partitioning operates in-place, so when recursive calls finish, the array is already globally sorted.
- **Computational Cost Analysis:**
- **Worst Case:** $\mathcal{O}(n^2)$. Occurs when at each step the partition is maximally unbalanced (one subproblem of size $n-1$ and one of size $0$). The recurrence relation is:

$$

T(n) = T(n-1) + T(0) + \Theta(n) = T(n-1) + \Theta(n) \implies T(n) = \Theta(n^2)

$$

(for instance, an already sorted array when choosing the last element as pivot).

- **Best Case:** $\mathcal{O}(n \log n)$. Occurs when partitioning splits the array exactly in half at each step:

$$

T(n) = 2T(n/2) + \Theta(n) \implies T(n) = \Theta(n \log n)

$$

- **Average Case:** $\mathcal{O}(n \log n)$. Even if partitions are unbalanced with a constant ratio (e.g., 90% and 10%), the recursion tree depth is $\mathcal{O}(\log n)$, and at each level the total partitioning cost is $\Theta(n)$. With a random pivot (_Randomized Quicksort_), the expected cost is strictly $\Theta(n \log n)$.
- **Space:** $\mathcal{O}(\log n)$ call stack space in the average case, $\mathcal{O}(n)$ in the worst case.
