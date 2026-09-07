---
title: "Define the properties that make a binary tree a min-heap and explain how the primi..."
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
  - "Define the properties that make a binary tree a min-heap and explain how the primi..."
---

# 🎴 Define the properties that make a binary tree a min-heap and explain how the primi...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ Define the properties that make a binary tree a min-heap and explain how the primitive that returns the minimum key from the tree works, justifying its correctness. If you wanted to find the maximum key stored in the heap, in which positions of the array (which implicitly implements the heap) would you need to search? Justify your answer. #card

?

- **Properties of a Min-Heap:**
- **Structural property:** It is a nearly complete binary tree, meaning it is completely filled on all levels except possibly the last, whose leaves are packed to the left.
- **Min-heap property:** For every node $v$ other than the root: $\text{key}(\text{Parent}(v)) \le \text{key}(v)$.
- **Primitive to return the minimum key (`Extract-Min`):**
- **Operation:**
- The minimum key is always found at the root ($H[0]$) and is saved to be returned.
- The last element of the array ($H[n-1]$) is moved to the root, and the size of the heap is decremented by 1.
- Since the new root may violate the min-heap property, `Min-Heapify(H, 0)` is called to restore the property by sifting the element down the tree, iteratively swapping it with the child having the smaller key.
- **Justification of correctness:** The root held the global minimum by the heap order property. Moving the last leaf to the root trivially preserves the shape of the nearly complete binary tree. The `Min-Heapify` procedure sifts the value down along a path by comparing it with its children: because it swaps the parent with the smaller of the two children, that child becomes the valid parent (smaller than the other child and the displaced root), restoring the property recursively at every level until stopping at a leaf.
- **Position of the maximum element in a Min-Heap:**
- The maximum element must reside in a **leaf**. _Justification:_ If the maximum were located in an internal node, it would have at least one child with a key greater than or equal to its own (by the min-heap property), contradicting the assumption that it is the global maximum.
- In an array of $n$ elements indexed from $0$ to $n-1$, leaves occupy exactly the positions from:

```text
≤ft {n}{2} to n - 1
```

Therefore, finding the maximum only requires scanning this second half of the array (costing $\mathcal{O}(n)$).
