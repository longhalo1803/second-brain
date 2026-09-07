---
title: "🗂 What is the pseudocode of HeapSort and what are its time and space complexities"
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
  - "🗂 What is the pseudocode of HeapSort and what are its time and space complexities"
---

# 🎴 🗂 What is the pseudocode of HeapSort and what are its time and space complexities

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🗂️🟢 What is the pseudocode of HeapSort and what are its time and space complexities? #card

?
**Pseudocode**:

```text
HeapSort(H)
    BuildHeap(H)                         // {#D9534F}{≤ftarrow Max-Heap construction {O}(n)}
    HeapSize := length(H) - 1            // {#D9534F}{≤ftarrow initializes the heap size}
    for i := length(H) - 1 downto 1 do
        H[i] := ExtractMaxHeap(H)            // {#D9534F}{≤ftarrow extracts max, decrements HeapSize and calls Heapify}
```

Show `ExtractMaxHeap(H)`

````text
ExtractMaxHeap(H)
    if HeapSize

📌 Note:
The version above treats the heap as a *priority queue*, using an external function that extracts the maximum, removes it from the heap, and returns it to reassign it to `H[i]`.
It correctly shows the reuse of the extraction function, but it creates unnecessary memory steps (saves the value in a temporary variable `max`, moves the last element to `H[0]`, and finally overwrites `H[i]` with `max`).
The following version works directly on the array in-place by swapping the root `H[0]` (the maximum) with the last element `H[i]`, then decreasing the heap size and calling `Heapify(H, 0)`.

**Pseudocode (Standard In-Place HeapSort)**:

```text
HeapSort(H)
    BuildHeap(H)                         // {#D9534F}{≤ftarrow Max-Heap construction {O}(n)}
    HeapSize := length(H) - 1            // {#D9534F}{≤ftarrow initializes the heap size}
    for i := length(H) - 1 downto 1 do
        swap H[0] with H[i]                  // {#D9534F}{≤ftarrow moves the maximum to the end}
        HeapSize := HeapSize - 1             // {#D9534F}{≤ftarrow decrements heap size}
        Heapify(H, 0)                        // {#D9534F}{≤ftarrow restores Max-Heap}
````

Show `Heapify(H, i)` and `BuildHeap(H)`

```text
Heapify(H, i)
    l := Left(i), r := Right(i), max := i
    if l ≤ HeapSize and H[l] > H[max] then max := l
    if r ≤ HeapSize and H[r] > H[max] then max := r
    if max ≠q i then
        swap H[i] with H[max]
        Heapify(H, max)
```

```text
BuildHeap(H)
    HeapSize := length(H) - 1
    for i := floor((length(H) - 2) / 2) downto 0 do
        Heapify(H, i)
```

(the loop above uses the explicit mathematical version equivalent to $\small\texttt{for }\textsf{i := Parent(HeapSize)} \texttt{ downto } \texttt{0}$)

**Time Complexity**:
Worst case: $\mathcal{O}(n \log n)$
Average case: $\mathcal{O}(n \log n)$
Best case: $\mathcal{O}(n \log n)$

**Space Complexity**:
$\mathcal{O}(1)$ auxiliary (_in-place_ sorting).
