---
title: "Explain how the HeapSort sorting algorithm works, justifying its correctness and p..."
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
  - "Explain how the HeapSort sorting algorithm works, justifying its correctness and p..."
---

# 🎴 Explain how the HeapSort sorting algorithm works, justifying its correctness and p...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Explain how the HeapSort sorting algorithm works, justifying its correctness and presenting its computational cost.

NOTE: pseudocode alone (even if commented) is not an acceptable answer to this question. #card
?

- **Operation of HeapSort:**
  The algorithm uses a Max-Heap to sort an array $A[0 \dots n-1]$ in-place:
- **Phase 1 (Building the Max-Heap):** Using the `Build-Max-Heap` procedure, it transforms the initial unsorted array into a Max-Heap. This is achieved by applying `Max-Heapify` backwards from the lowest internal nodes up to the root, from index $\lfloor n/2 \rfloor - 1$ down to $0$.
- **Phase 2 (Repeated extraction and sorting):**
  Since the maximum element is at the root ($A[0]$):
- Swap $A[0]$ with the last element of the current heap $A[i]$ (with $i$ decreasing from $n-1$ down to $1$).
- The maximum element is now in its final sorted position at the end of the array.
- Decrease heap size by 1, excluding the newly placed element.
- Restore the Max-Heap property at the new root by calling `Max-Heapify(A, 0)` on the remaining portion ($0 \dots i-1$).
- **Justification of Correctness:**
  The loop invariant ensures that at the start of each iteration $i$, subarray $A[0 \dots i]$ is a valid Max-Heap containing the $i+1$ smallest elements of the original array, while subarray $A[i+1 \dots n-1]$ contains the remaining elements already sorted and all greater than or equal to any element in $A[0 \dots i]$. At each step, the swap places the maximum of the remaining elements at position $i$. When the iterations complete (when heap size is 1), the entire array is sorted in non-decreasing order.
- **Computational Cost:**
- `Build-Max-Heap` takes linear time $\mathcal{O}(n)$.
- The loop performs $n - 1$ swaps and extractions. Each call to `Max-Heapify` takes time proportional to the height of the heap, which is $\mathcal{O}(\log n)$.
- Therefore, the extraction phase takes $(n-1) \cdot \mathcal{O}(\log n) = \mathcal{O}(n \log n)$. The total time is $\mathcal{O}(n) + \mathcal{O}(n \log n) = \Theta(n \log n)$ across all cases (best, worst, and average). Auxiliary space is $\mathcal{O}(1)$ because it sorts in-place.
