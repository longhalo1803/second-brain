---
title: "How is a Priority Queue implemented using a Min-Heap, and how is DecreasePriority..."
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
  - "How is a Priority Queue implemented using a Min-Heap, and how is DecreasePriority..."
---

# 🎴 How is a Priority Queue implemented using a Min-Heap, and how is DecreasePriority...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is a Priority Queue implemented using a Min-Heap, and how is `Decrease_Priority` handled using Handles? #card

?
In a Min-Heap of pairs `Q[i] = (el, pr)` ordered with respect to the priorities `pr`, to invoke `Decrease_Priority(Q, el, pr)` one needs to know the **position index** where element `el` resides in the heap array in order to call `DecreaseKeyHeap(Q, i, pr)`.

**Problem**: A linear search for `el` in the heap array would take $\mathcal{O}(n)$, nullifying the advantages of the heap.

**Solution (Handle / Position Array)**:
If the elements `el` are identified by unique integers in $\{0, 1, \dots, n-1\}$, an auxiliary structure `Pos` is used where:

$$

\text{Pos}[\text{el}] = \text{index of el in the heap array}

$$

Every time two heap elements swap positions during a `Heapify` or `DecreaseKeyHeap`, their respective entries in `Pos` are updated in $\mathcal{O}(1)$. In this way, the index of `el` can be retrieved in $\mathcal{O}(1)$ and the entire `Decrease_Priority` is executed in $\mathcal{O}(\log n)$.
