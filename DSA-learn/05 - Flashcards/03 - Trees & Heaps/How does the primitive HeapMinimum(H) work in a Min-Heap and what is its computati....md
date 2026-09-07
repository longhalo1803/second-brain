---
title: "How does the primitive HeapMinimum(H) work in a Min-Heap and what is its computati..."
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
  - "How does the primitive HeapMinimum(H) work in a Min-Heap and what is its computati..."
---

# 🎴 How does the primitive HeapMinimum(H) work in a Min-Heap and what is its computati...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How does the primitive `HeapMinimum(H)` work in a Min-Heap and what is its computational cost? #card

?
Returns (without deleting) the minimum value stored in the heap, which due to the heap-order property is always located at the root (positioned at index 0 of the array).

**Pseudocode**:

```text
HeapMinimum(H)
    if HeapSize < 0
        then return error
        else return H[0]
```

**Computational Cost**: $\mathcal{O}(1)$.
