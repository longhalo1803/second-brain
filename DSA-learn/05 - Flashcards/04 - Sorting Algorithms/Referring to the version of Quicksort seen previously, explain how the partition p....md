---
title: "Referring to the version of Quicksort seen previously, explain how the partition p..."
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
  - "Referring to the version of Quicksort seen previously, explain how the partition p..."
---

# 🎴 Referring to the version of Quicksort seen previously, explain how the partition p...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Referring to the version of Quicksort seen previously, explain how the partition procedure works. Commented pseudocode is not a sufficient explanation, and including it is not required. #card

?
The procedure `Partition(A, p, r)` (considering canonical Lomuto partition) has the essential task of rearranging a subarray $A[p \dots r]$ in-place around a pivot element.

- **Pivot Selection:**
  The element at the right end of the subarray is taken as the pivot, namely $x = A[r]$.
- **Pointers and Invariant:**
  The procedure maintains two moving indices, $i$ and $j$, that conceptually partition the array into four contiguous segments:
- Index $i$ tracks the boundary of the region of values less than or equal to the pivot. It is initially set to $p-1$.
- Index $j$ linearly scans elements from the first ($p$) up to the second-to-last ($r-1$). As it advances, the partition invariant holds:
- For every index $k \in [p \dots i]$, $A[k] \le x$.
- For every index $k \in [i+1 \dots j-1]$, $A[k] > x$.
- The slice $[j \dots r-1]$ contains elements not yet examined.
- Cell $A[r]$ contains pivot $x$.
- **Loop Progression:**
  At each step, compare the current element $A[j]$ with pivot $x$:
- If $A[j] > x$, the element belongs to the "greater" region: simply increment index $j$.
- If $A[j] \le x$, the element must enter the "less than or equal" region: first increment index $i$ (expanding the first region) and swap $A[i]$ with $A[j]$. Then increment $j$.
- **Finalization and Pivot Placement:**
  Once all elements have been scanned (when $j = r$), all elements from $p$ to $i$ are $\le x$ and all from $i+1$ to $r-1$ are $> x$. A final swap is made between $A[i+1]$ and pivot $A[r]$.
  In this way, the pivot ends up at its correct final sorted position ($i+1$), cleanly separating the two subsets. The procedure returns index $i+1$. The time taken is strictly linear: $\Theta(n)$, where $n = r - p + 1$.
