---
title: "Compare the computational complexities of the operations of a Priority Queue imple..."
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
  - "Compare the computational complexities of the operations of a Priority Queue imple..."
---

# 🎴 Compare the computational complexities of the operations of a Priority Queue imple...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Compare the computational complexities of the operations of a Priority Queue implemented using Unsorted Lists, Sorted Lists, and a Min-Heap. #card

?
OperationUnsorted ListSorted List**Min-Heap**`BuildQueue(Q)`$\mathcal{O}(n)$$\mathcal{O}(n \log n)$**$\mathcal{O}(n)$**`MinQueue(Q)`$\mathcal{O}(n)$$\mathcal{O}(1)$**$\mathcal{O}(1)$**`DeQueue(Q)`$\mathcal{O}(n)$$\mathcal{O}(1)$**$\mathcal{O}(\log n)$**`EnQueue(Q, e, p)`$\mathcal{O}(1)$$\mathcal{O}(n)$**$\mathcal{O}(\log n)$**
📌 Note:
The Min-Heap provides the best overall balance between insertion/extraction ($\mathcal{O}(\log n)$) and construction/access to the minimum ($\mathcal{O}(n)$ and $\mathcal{O}(1)$).
