---
title: "What is the pseudocode of InsertionSort (and why is an inner while loop used)"
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
  - "What is the pseudocode of InsertionSort (and why is an inner while loop used)"
---

# 🎴 What is the pseudocode of InsertionSort (and why is an inner while loop used)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🟢 What is the pseudocode of InsertionSort (and why is an inner `while` loop used)?

_(Try executing with the example *$A=[5,2,4,7]$* to verify that it works)_ #card
?
**Pseudocode:**

```text
InsertionSort(A, n)
    for j := 1 to n - 1 do
        i := j - 1
                    tmp := A[j] \,// save element to insert
        while (i ≥ 0 AND A[i] > tmp) do
                A[i+1] := A[i] // shift right elements > tmp
                        i := i - 1 \;\,// move down sorted portion
            A[i+1] := tmp \;\,\;// insert tmp
```

📌 Note: we start from the second element because the first element, taken alone, is already sorted.

**Loop structure:**

- **Outer loop (`for`):** iterates through the elements to be inserted, from $j=1$ to $n-1$.
- **Inner loop (`while`):** shifts elements greater than $\textsf{tmp}$ to the right. A `while` (and not a `for`) is used because the number of steps is not fixed, but stops early as soon as the correct position for $\textsf{tmp}$ is found.

Alternative version with swap:

```text
InsertionSort(A, n)
    for i := 1 to n - 1 do
        j := i
        while (j > 0 AND A[j]  0 AND A[j]  A[j+1];\ j := j - 1) do
            swap(A[j], A[j+1])
```

$\begin{array}{l} \textsf{InsertionSort(A, n)} \\ \quad \texttt{for } \textsf{i := 1} \texttt{ to } \textsf{n - 1} \texttt{ do} \\ \quad\quad \texttt{for } \textsf{j := i} \texttt{ downto } \textsf{1} \texttt{ while } \textsf{A[j]
(⚠️ Note: in the first algorithm and in the pseudocode of these flashcards, loop indices generally follow the convention used by the CLRS book (_Introduction to Algorithms_), while in the second version of insertion sort in this case the standard convention $i$-outer-loop $j$-inner-loop was used)

By Suaudeau - Own work, CC BY-SA 4.0, Link
