---
title: "What is the recurrence equation for the running time of QuickSort"
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
  - "What is the recurrence equation for the running time of QuickSort"
---

# 🎴 What is the recurrence equation for the running time of QuickSort

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the recurrence equation for the running time of QuickSort? #card

?
Given an array of size $n$, the general recurrence equation is:

$$
T(n) = \begin{cases} 0 & \text{if } n = 0, 1 \\ T(q) + T(n - q - 1) + n - 1 & \text{otherwise} \end{cases}
$$

where $q$ is the size of the left subarray produced by `Partition`, $n-q-1$ is the size of the right subarray, and $n - 1$ represents the cost (number of comparisons) of the partitioning operation on $n$ elements.

$\begin{array}{ll}
\textsf{QuickSort}(A, p, r) & \\
\quad \texttt{if } p < r \texttt{ then} & \color{#D36B7B}{\scriptstyle \text{// } T(0) = 0 \text{ if } p \ge r \text{ (base case)}} \\
\quad\quad q := \textsf{Partition}(A, p, r) & \color{#D36B7B}{\scriptstyle \text{// } + \, (n - 1) \text{ (comparisons executed by Partition)}} \\
\quad\quad \textsf{QuickSort}(A, p, q-1) & \color{#D36B7B}{\scriptstyle \text{// } + \, T(q) \text{ (cost of left subproblem)}} \\
\quad\quad \textsf{QuickSort}(A, q+1, r) & \color{#D36B7B}{\scriptstyle \text{// } + \, T(n - q - 1) \text{ (cost of right subproblem)}}
\end{array}$
