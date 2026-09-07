---
title: "Define the Heap data structure in its ”original” tree-based version, and explain h..."
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
  - "Define the Heap data structure in its ”original” tree-based version, and explain h..."
---

# 🎴 Define the Heap data structure in its ”original” tree-based version, and explain h...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ Define the Heap data structure in its ”original” tree-based version, and explain how it can be implemented using an array. Choose one of the primitives of the Heap data structure and explain how it can be implemented. #card

?

- **Definition of the Tree-based Heap:**
  A binary heap is a binary tree that satisfies two properties:
- **Shape property (nearly complete tree):** All levels are completely filled except possibly the last one, which is filled from left to right without gaps.
- **Heap order property:** For every node $x$ other than the root:
- In a _Max-Heap_: $\text{key}(\text{parent}(x)) \ge \text{key}(x)$.
- In a _Min-Heap_: $\text{key}(\text{parent}(x)) \le \text{key}(x)$.
- **Implicit Representation via Array:**
  Thanks to the shape property, the heap can be stored in an array $H$ without explicit pointers:
- The root is located at $H[0]$.
- Given a node at index $i$:
- $\text{LeftChild}(i) = 2i + 1$
- $\text{RightChild}(i) = 2i + 2$
- $\text{Parent}(i) = \lfloor \frac{i-1}{2} \rfloor$
- This allocation avoids pointer memory overhead and guarantees excellent cache locality.
- **Implementation of a Primitive: `Max-Heapify(H, i)`:**
  The procedure assumes that the subtrees rooted at the children of $i$ are already valid max-heaps, but $H[i]$ might violate the heap property.
- Identify the left child $l = 2i+1$ and right child $r = 2i+2$.
- Compare $H[i]$ with $H[l]$ and $H[r]$, finding the index of the maximum among the three nodes (`max`).
- If `max` $\ne i$:
- Swap the value of $H[i]$ with $H[\text{max}]$.
- Recursively call `Max-Heapify(H, max)` to push the violation down to the leaves if needed. _Cost:_ The height of the tree is $\lfloor \log_2 n \rfloor$, so the worst-case cost is $\mathcal{O}(\log n)$.
