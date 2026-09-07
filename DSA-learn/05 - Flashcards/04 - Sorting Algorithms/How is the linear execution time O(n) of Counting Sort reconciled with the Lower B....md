---
title: "How is the linear execution time O(n) of Counting Sort reconciled with the Lower B..."
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
  - "How is the linear execution time O(n) of Counting Sort reconciled with the Lower B..."
---

# 🎴 How is the linear execution time O(n) of Counting Sort reconciled with the Lower B...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How is the linear execution time $O(n)$ of Counting Sort reconciled with the _Lower Bound theorem_ for comparison-based sorting, which establishes a lower bound equal to $\Omega(n \log n)$? #card

?
The lower bound $\Omega(n \log n)$ applies **exclusively** to sorting algorithms **based on comparisons** between pairs of elements (such as QuickSort, MergeSort, HeapSort).

**Counting Sort does not violate the lower bound** because ****it performs NO comparisons**** between the elements of $A$.

It exploits the nature of the data (integers within $[0, k]$) and performs direct accesses to the cells of array $C$ using the values of $A$ as **indices**. Therefore, it can break the $\Omega(n \log n)$ barrier and perform sorting in linear time $\Theta(n)$ when $k \in O(n)$.
