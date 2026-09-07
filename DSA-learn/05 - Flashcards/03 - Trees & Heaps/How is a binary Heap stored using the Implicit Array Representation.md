---
title: "How is a binary Heap stored using the Implicit Array Representation"
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
  - "How is a binary Heap stored using the Implicit Array Representation"
---

# 🎴 How is a binary Heap stored using the Implicit Array Representation

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is a binary Heap stored using the Implicit Array Representation? #card

?
Thanks to the structural property, a binary heap can be represented compactly using a simple array `H`, without explicitly storing pointers to children or parent.

The heap keys are inserted into the array **level by level** and, for each level, **from left to right**.

**Array control variables**:

- `HeapLength`: the total allocated size for the array (last index of the array).
- `HeapSize`: the last index of the array containing a valid heap key ($\text{HeapSize} \le \text{HeapLength}$).
  📝 **Correspondence example**:
  If the root resides at `H[0]`:
- Level 0: `H[0]`
- Level 1: `H[1], H[2]`
- Level 2: `H[3], H[4], H[5], H[6]`
