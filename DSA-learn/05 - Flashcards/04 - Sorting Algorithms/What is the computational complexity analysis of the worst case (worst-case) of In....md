---
title: "What is the computational complexity analysis of the worst case (worst-case) of In..."
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
  - "What is the computational complexity analysis of the worst case (worst-case) of In..."
---

# 🎴 What is the computational complexity analysis of the worst case (worst-case) of In...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the computational complexity analysis of the **worst case** (worst-case) of InsertionSort? #card

?
$\begin{array}{ll}
\textsf{InsertionSort(A, n)} & \\
\quad \texttt{for } \textsf{j := 1} \texttt{ to } \textsf{n - 1} \texttt{ do} & \\
\quad\quad \textsf{i := j - 1} & \\
\quad\quad \textsf{tmp := A[j]} & \\
\quad\quad \texttt{while } (\textsf{i} \ge \texttt{0} \texttt{ AND } \textsf{A[i]} > \textsf{tmp}) \texttt{ do} & \\
\quad\quad\quad \textsf{A[i+1] := A[i]} & \\
\quad\quad\quad \textsf{i := i - 1} & \\
\quad\quad \textsf{A[i+1] := tmp} &
\end{array}$

**Upper Bound:**
The outer loop is executed for $j$ from $1$ to $n-1$. For a fixed $j$, the `while` loop executes **AT MOST** $j$ comparisons (when $\textsf{tmp}$ is compared with all values from $j-1$ down to 0).

$$
T(n) \le \sum_{j=1}^{n-1} j = \frac{(n-1)n}{2} \implies T(n) \in O(n^2)
$$

**Lower Bound:**
Does there exist an input instance for which the algorithm must perform exactly $j$ comparisons for each $j$?
**Yes:** when the input sequence has all distinct values and is **sorted in descending order**. At each iteration, the element at position $j$ must shift until it ends up at position 0.

$$
T(n) \ge \sum_{j=1}^{n-1} j = \frac{(n-1)n}{2} \implies T(n) \in \Omega(n^2)
$$

**Therefore, the worst case has cost: **$T(n) \in \Theta(n^2)$.
