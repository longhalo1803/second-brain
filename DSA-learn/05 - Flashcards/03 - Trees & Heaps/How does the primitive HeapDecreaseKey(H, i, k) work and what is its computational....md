---
title: "How does the primitive HeapDecreaseKey(H, i, k) work and what is its computational..."
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
  - "How does the primitive HeapDecreaseKey(H, i, k) work and what is its computational..."
---

# 🎴 How does the primitive HeapDecreaseKey(H, i, k) work and what is its computational...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How does the primitive `HeapDecreaseKey(H, i, k)` work and what is its computational cost? #card

?
**Decreases the value of the key at position** $i$ by setting it to the new value $k \le H[i]$.
However, it does not stop there: since the key becomes smaller, the Min-Heap property may be violated with respect to the parent. The procedure **restores the property by making the key **bubble up**** (_swim / percolate up_) through successive swaps with the parent.

**Pseudocode**:

```text
HeapDecreaseKey(H, i, k)
    if i > HeapSize OR k > H[i]
        then return error
    H[i] := k
    while i > 0 AND H[Parent(i)] > k do
        Swap H[i] with H[Parent(i)]
        i := Parent(i)
```

**Computational Cost**: $\mathcal{O}(\log n)$, equal to the maximum height that can be climbed in the tree.
