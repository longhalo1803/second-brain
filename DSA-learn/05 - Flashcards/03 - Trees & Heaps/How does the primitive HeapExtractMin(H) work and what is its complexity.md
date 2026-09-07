---
title: "How does the primitive HeapExtractMin(H) work and what is its complexity"
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
  - "How does the primitive HeapExtractMin(H) work and what is its complexity"
---

# 🎴 How does the primitive HeapExtractMin(H) work and what is its complexity

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How does the primitive `HeapExtractMin(H)` work and what is its complexity? #card

?
Returns and removes the minimum element present in the heap.
Saves the value in `H[0]`, overwrites it with the last element of the array (`H[HeapSize]`), decrements `HeapSize`, and invokes `Heapify(H, 0)` to restore the heap property starting from the root.

**Pseudocode**:

```text
HeapExtractMin(H)
    if HeapSize Heapify$\small\begin{array}{ll}
\textsf{Heapify(H, i)} & \\
\quad \texttt{if }\textsf{i} > \textsf{HeapSize} \texttt{ then return }\textsf{error} & \\
\quad \textsf{min := i} & \\
\quad \textsf{l := LeftChild(i)} & \\
\quad \textsf{r := RightChild(i)} & \\
\quad \small\color{gray}\textsf{// Comparison with the left child (if it exists)} & \\
\quad \texttt{if }\textsf{l} \le \textsf{HeapSize} \texttt{ AND } \textsf{H}\texttt{[}\textsf{l}\texttt{]}

**Computational Cost**: $\mathcal{O}(\log n)$.

Extract Maximum (not minimum, but similar operation):
```
