---
title: "How does the primitive HeapInsertKey(H, k) work and what is its complexity"
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
  - "How does the primitive HeapInsertKey(H, k) work and what is its complexity"
---

# 🎴 How does the primitive HeapInsertKey(H, k) work and what is its complexity

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How does the primitive `HeapInsertKey(H, k)` work and what is its complexity? #card

?
Inserts a new key $k$ into the heap.
Increments `HeapSize`, inserts the new key into the first free position (at the end of the array), and then calls `HeapDecreaseKey` to move the key up to its correct position.

**Pseudocode**:

```text
HeapInsertKey(H, k)
    if HeapSize = HeapLength
        then return error
    HeapSize := HeapSize + 1
        {gray}{H[HeapSize] := k} {gray}{ // redundant}
    HeapDecreaseKey(H, HeapSize, k)
```

📌 Redundancy: `H[HeapSize] := k` is redundant because the overwrite/assignment already occurs inside `HeapDecreaseKey(H, i, k)`. It is included here merely to show conceptually the positioning prior to the update.

**Computational Cost**: $\mathcal{O}(\log n)$.

📌 Note:

- `HeapLength`: the total allocated size for the array (last index of the array).
- `HeapSize`: the last index of the array containing a valid heap key ($\text{HeapSize} \le \text{HeapLength}$).❓ Why not use Heapify?
  `HeapDecreaseKey` is used because the new value is inserted at the last position of the array (a leaf at the bottom of the tree), so the only direction to restore the structure is **bubbling up toward the root**.
- **`HeapDecreaseKey` (Ascent / Bottom-Up)** compares the node inserted at the bottom with its **parent** and moves it upward until the Min-Heap order is satisfied.
- **`Heapify` (Descent / Top-Down)** pushes an element downward by comparing it with its **children**. Being applied to a leaf at the bottom of the heap, `Heapify` would find no children, terminating immediately without making swaps and leaving the new element stuck at the bottom.
