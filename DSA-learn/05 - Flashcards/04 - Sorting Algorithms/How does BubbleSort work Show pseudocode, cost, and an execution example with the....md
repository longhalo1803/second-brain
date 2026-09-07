---
title: "How does BubbleSort work Show pseudocode, cost, and an execution example with the..."
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
  - "How does BubbleSort work Show pseudocode, cost, and an execution example with the..."
---

# 🎴 How does BubbleSort work Show pseudocode, cost, and an execution example with the...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: \*How does BubbleSort work? Show pseudocode, cost, and an execution example with the initial array: `[5, 1, 4, 2]` #card

?
BubbleSort is an elementary (and inefficient) sorting algorithm that repeatedly iterates through the input list, comparing adjacent pairs of elements $A[i]$ and $A[i+1]$ and swapping them if they are not in the correct order.
With each complete iteration, the largest element "bubbles up" to its final position at the end of the array. The process repeats until the list is sorted.

- **Worst / Average Case Complexity:** $O(n^2)$
- **Best Case Complexity:** $O(n)$ (if optimized with a swap-tracking flag)
- **Invariant:** After $i$ passes, the last $i$ elements are sorted and are the largest of the entire array.

**Elementary version pseudocode:**

```text
BubbleSort(A, n)
    for i := 0 to n - 2 do
        for j := 0 to n - 2 - i do
            if A[j] > A[j+1] then
                swap A[j] with A[j+1]
```

**General state at pass **$i$**:**

$$
\underbrace{
\overset{\text{0}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\text{n-i-1}}{{\vphantom{\text{unsorted}}\dots}}
}_{\small\text{n - i elements left to sort}}
\underbrace{
\overset{\text{n-i}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{sorted}}
\overset{\text{n-1}}{{\vphantom{\text{unsorted}}\dots}}
}_{\small\text{i elements already in right place (i maxes)}}
$$

**Local comparison and swap (**$A[j]$** vs **$A[j+1]$**):**

If $A[j] > A[j+1]$, the two elements are swapped, pushing the larger value to the right:

$$
\overset{\text{0}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\large\color{#E65100}{\curvearrowright}}{
\overset{\text{j}}{{\vphantom{\text{unsorted}}\dots}}
\overset{\text{j+1}}{{\vphantom{\text{unsorted}}\dots}}
}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\text{n-1}}{{\vphantom{\text{unsorted}}\dots}}
$$

**Execution example:**

Initial array: `[5, 1, 4, 2]`

- $i = 0$:
- Compare 5 and 1 $\rightarrow$ swap: `[1, 5, 4, 2]`
- Compare 5 and 4 $\rightarrow$ swap: `[1, 4, 5, 2]`
- Compare 5 and 2 $\rightarrow$ swap: `[1, 4, 2, **5**]` (5 is in its place)
- $i = 1$:
- Compare 1 and 4 $\rightarrow$ OK: `[1, 4, 2, **5**]`
- Compare 4 and 2 $\rightarrow$ swap: `[1, 2, **4**, **5**]` (4 is in its place)
- $i = 2$:
- Compare 1 and 2 $\rightarrow$ OK: `[**1**, **2**, **4**, **5**]` (Sorted array)

**Optimized version pseudocode:**

BubbleSort(A, n)
swapped := true
while swapped do
swapped := false
for i := 0 to n - 2 do
if A[i] > A[i+1] then
swap A[i] and A[i+1]
swapped := true
n := n - 1

In this version there are two optimizations compared to the first:
**`n := n - 1`**: avoids rechecking the last elements (the tail) that have already reached their destination. Reduces the number of comparisons by 1 on each pass.
**flag `swapped`**: used to determine if the array (or what remains of it) is already entirely sorted. If it completes an entire pass from 0 to n-2 without a single swap, it means all remaining elements are already in ascending order. There is no point in continuing to run further loops.

**Time complexity analysis:**

- **Worst Case:** $\Theta(n^2)$

      *(occurs when the array is sorted in descending order; performs $\frac{n(n-1)}{2}$ comparisons and swaps).*

- **Average Case:** $\Theta(n^2)$
- **Best Case:** $\Theta(n)$

      *(with the optimization using the `swapped` variable, if the array is already sorted, it stops after just 1 single scan of $n-1$ comparisons).*

By Simpsons contributor - Own work, CC BY-SA 3.0, Link
