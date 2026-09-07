---
title: "Exercise 10"
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
  - "Exercise 10"
---

# 🎴 Exercise 10

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Exercise 10

Answer the following questions, justifying your answer (a proof is not necessary, but provide a thorough explanation):

1. With an example, show that `Quicksort` (Lomuto or Hoare) is not stable.
2. Is the covered `SelectionSort` sorting algorithm stable?
3. Is the covered `InsertionSort` sorting algorithm stable?
4. Is the covered `MergeSort` sorting algorithm stable?

📌 Note: a sorting algorithm is stable when equal values appear, in the final sorted sequence, in the same order they were in the initial one. #card
?
**1. Quicksort: IS NOT STABLE**
Counterexample: consider the sequence $\langle 4, 8_1, 8_2, 8_3, 10, 5 \rangle$.
Executing `Partition` with pivot 5 (in the last position), element 5 is swapped with the first element greater than 5 ($8_1$).
The relative position of the blue 8 ($8_1$) with respect to the other two 8s changes in the final sequence, therefore this version of Partition/Quicksort is not stable.

**2. SelectionSort: IS NOT STABLE**
Counterexample: consider the sequence $\langle 4, 8_1, 8_2, 8_3, 10, 5 \rangle$.
At iteration $i=1$, we search for the minimum in the subsequence $\langle 8_1, 8_2, 8_3, 10, 5 \rangle$.
The minimum is 5 and is swapped with $A[1] = 8_1$. In this way $8_1$ is moved after $8_2$ and $8_3$, changing the initial relative order.

**3. InsertionSort: IS STABLE**
Proof by induction: we prove that at the beginning of iteration $j$, the portion $A[0..j-1]$ is stably sorted.

- _Base case:_ At the beginning of the first iteration ($j=1$), $A[0]$ contains a single element, so it is stably sorted.

- _Inductive hypothesis:_ At the beginning of iteration $j$, $A[0..j-1]$ is stably sorted.

- _Inductive step:_ In iteration $j$, we compare $A[j]=x$ with the preceding elements from right to left.
  **If $x$ is not yet present**, it is inserted in the correct position and the right shift of greater elements maintains its stability.
  **If $x$ is already present** in $A[0..j-1]$, the algorithm stops as soon as it encounters an element $\le x$. The new occurrence of $x$ is placed immediately to the right of the first $x$ found moving from right to left (i.e., to the right of all previously found occurrences), making the new ordering stable.

      Case 1: the value *x* is not already present in *A[0..j - 1]*.









      Case 2: the value *x* is already present in *A[0..j - 1]*.

**4. MergeSort: IT IS STABLE**
Proof by induction (it is a very useful tool to prove correctness properties of algorithms based on the Divide-and-Conquer technique).

First, let us observe that during the Divide phase, the elements of the sequence are not swapped. Therefore, when Merge merges the sequences $A[i..k]$ and $A[k+1..j]$, it sorts elements that originally were in $A[i..j]$.
So, assuming that $A[i..k]$ and $A[k+1 .. j]$ are stably sorted, we must show that Merge maintains this stability when generating the sorted sequence $A[i..j]$. We then proceed with a proof by induction on the size $d = j - i + 1$ of $A[i..j]$.

**Base case**: For $d = 1$, the only value of the subsequence remains in its place, and therefore $A[i..i]$ is stable.

**Inductive hypothesis**: For $h \in \{1, \dots, d-1\}$, the sequences $A[i..j]$, for $h = j - i + 1$, generated in the Divide phase have been stably sorted by Merge.

**Inductive step**: we show that Merge stably sorts the sequence $A[i..j]$ for $h = d$ generated in the Divide phase.

By the inductive hypothesis, the subsequences $A[i..k]$ and $A[k+1 .. j]$ are stably sorted. During the execution of Merge, the following cases can occur:

- The equal elements $e_1 = e_2 = \dots = e_p$ are located in only one of the partitions and are copied into $B$. These elements will be copied one by one from left to right and will end up in the same order as they appeared in the starting subsequence. They will retain the same order even when copied back into $A$.
- The equal elements $e_1 = e_2 = \dots = e_p$ are located in the left partition and $e'_1 = e'_2 = \dots = e'_{p'}$, equal to the former (that is, $e_1 = e'_1$), are located in the right portion and are copied into $B$. As before, elements from the same subsequence are copied into $B$ in the same order. Furthermore, since the comparison between elements of the two subsequences is performed using a $\le$, those in the left subsequence will be copied first, followed by those in the right subsequence. Since originally in $A$, the elements $e_1 = e_2 = \dots = e_p$ were to the left of the elements $e'_1 = e'_2 = \dots = e'_{p'}$, the final sequence turns out to be stable.
- The equal elements $e_1 = e_2 = \dots = e_p$ are not copied into $B$: (1) if they belonged to the right sequence, they are not moved, so if they were stable before, they will remain so afterward. (2) if they belonged to the left sequence, they are copied at the end of $A[i..j]$ in the same order in which they were before, so if they were stable before, they will remain so afterward.
- The equal elements $e_1 = e_2 = \dots = e_p$ are partially copied into $B$ and partially not:
  This situation occurs when one of the two subsequences is exhausted before the other while elements are still being compared and copied.

- If the right subsequence is exhausted, the remaining equal elements of the left subsequence (not yet copied into $B$) are simply copied at the end of $A[i..j]$ preserving their relative order, and since they were already to the left of any equal right elements already taken, stability is maintained.
- If the left subsequence is exhausted, it means all left elements (including any equal elements) have already been copied into $B$; the remaining equal elements on the right do not need to be moved and maintain their final relative position, thus preserving overall stability.

$$
\begin{array}{|l|c|c|c|c|c|}
\hline
\textbf{Algorithm} & \textbf{Best Time} & \textbf{Average Time} & \textbf{Worst Time} & \textbf{Space Cost} & \textbf{Stability} \\
\hline
\text{Selection Sort} & O(n^2) & O(n^2) & O(n^2) & O(1) & \text{Unstable} \\
\hline
\text{Insertion Sort} & O(n) & O(n^2) & O(n^2) & O(1) & \text{Stable} \\
\hline
\text{Merge Sort} & O(n \log n) & O(n \log n) & O(n \log n) & O(n) & \text{Stable} \\
\hline
\text{Quick Sort} & O(n \log n) & O(n \log n) & O(n^2) & O(\log n) & \text{Unstable} \\
\hline
\end{array}
$$
