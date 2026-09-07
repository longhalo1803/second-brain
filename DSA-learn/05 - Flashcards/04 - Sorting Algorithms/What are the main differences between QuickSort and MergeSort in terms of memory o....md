---
title: "What are the main differences between QuickSort and MergeSort in terms of memory o..."
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
  - "What are the main differences between QuickSort and MergeSort in terms of memory o..."
---

# 🎴 What are the main differences between QuickSort and MergeSort in terms of memory o...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the main differences between QuickSort and MergeSort in terms of memory occupation, worst case, and practical performance? #card

?
PropertyQuickSortMergeSort**Memory Usage\*\***In-place** (additional space $O(1)$ besides the call stack)**Not in-place** (requires an auxiliary array of size $O(n)$)**Worst-case Complexity**$\Theta(n^2)$ (deterministic)$\Theta(n \log n)$**Average/Expected Complexity**$\Theta(n \log n)$$\Theta(n \log n)$**Practical Efficiency\*\*Faster than MergeSort because it works in-place and thus uses less cacheGenerally slower than QuickSort due to auxiliary memory transfers
