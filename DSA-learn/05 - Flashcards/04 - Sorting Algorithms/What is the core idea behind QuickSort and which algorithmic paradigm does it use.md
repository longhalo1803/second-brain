---
title: "What is the core idea behind QuickSort and which algorithmic paradigm does it use"
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
  - "What is the core idea behind QuickSort and which algorithmic paradigm does it use"
---

# 🎴 What is the core idea behind QuickSort and which algorithmic paradigm does it use

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the core idea behind QuickSort and which algorithmic paradigm does it use? #card

?
QuickSort uses the **Divide and Conquer** technique to sort an array:

- **DIVIDE:** Selects an element of the array as a _pivot_ (e.g., at position $t$). Rearranges the array by moving all elements $\le A[t]$ to the left and all elements $> A[t]$ to the right, finally placing the pivot into its final index $q$.
- **CONQUER:** Recursively sorts the two sub-arrays $A[p .. q-1]$ and $A[q+1 .. r]$.
- **COMBINE:** No operation is required (the array is already sorted in place).**Base case:** when the sub-array has 0 or 1 element (i.e., when $p \ge r$), it is trivially solved and already sorted.

https://algorithms-visual.com/quicksort/ (partizione Lomuto)

(📌 Note on "`equal but 50% lucky`": used for handling duplicate values. When the algorithm encounters an element equal to the pivot, it applies a random 50% choice to decide which side to place it on, to avoid having all duplicates end up in the same sublist, ensuring balanced partitions and preventing performance degradation from $O(n \log n)$ to the worst case $O(n^2)$)
