---
title: "How does the procedure BuildHeap(H) work to convert a generic array into a Heap"
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
  - "How does the procedure BuildHeap(H) work to convert a generic array into a Heap"
---

# 🎴 How does the procedure BuildHeap(H) work to convert a generic array into a Heap

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How does the procedure `BuildHeap(H)` work to convert a generic array into a Heap? #card

?
Transforms an unsorted array `H` into a valid Heap by applying the `Heapify` procedure in a bottom-up fashion, starting from node `Parent(HeapSize)` down to the root (index 0).

📌 **Why start from Parent(HeapSize)?**
The nodes with indices from $\text{Parent}(\text{HeapSize})+1$ to $\text{HeapSize}$ are all leaves. Each leaf is already trivially a valid heap of height 0, so it does not require any call to `Heapify`.

**Pseudocode**:

```text
BuildHeap(H)
    HeapSize := length(H) - 1
    HeapLength := length(H) - 1
    for i := Parent(HeapSize) downto 0 do
        Heapify(H, i)
```

📌 Note: using `Parent(HeapSize)` makes the intent of the algorithm clear: start from the last non-leaf node (i.e., the parent of the last element in the heap) and work backwards to root 0. This avoids executing Heapify on the leaves, which are already trivially Max-Heaps/Min-Heaps.
