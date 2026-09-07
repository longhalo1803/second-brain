---
title: "What is the primitive Heapify(H, i) in a Min-Heap and how does it work"
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the primitive Heapify(H, i) in a Min-Heap and how does it work"
---

# 🎴 What is the primitive Heapify(H, i) in a Min-Heap and how does it work

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the primitive `Heapify(H, i)` in a Min-Heap and how does it work? #card

?
Restores the heap-order property following an increase in the value of the key at position $i$ (or decrease in a max-heap).
Assumes that the subtrees rooted at the children of $i$ are already valid Min-Heaps. The procedure **makes the key **bubble down**** (_sink / percolate down_) **by recursively swapping it with the minimum-value child** (or maximum for max-heap).

**Pseudocode**:

```text
Heapify(H, i)
    if i > HeapSize then return error
    min := i
    l := LeftChild(i)
    r := RightChild(i)
    {gray}// Comparison with the left child (if it exists)
    if l ≤ HeapSize AND H[l]  \text{HeapSize}$ (or $r > \text{HeapSize}$), it means that node has no left (or right) child. The last level of a heap might be only partially filled.

**Computational Cost**: $\mathcal{O}(\log n)$.
```
