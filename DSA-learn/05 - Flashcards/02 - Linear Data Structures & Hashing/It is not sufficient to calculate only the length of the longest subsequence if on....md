---
title: "It is not sufficient to calculate only the length of the longest subsequence if on..."
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "It is not sufficient to calculate only the length of the longest subsequence if on..."
---

# 🎴 It is not sufficient to calculate only the length of the longest subsequence if on...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: It is not sufficient to calculate only the length of the longest subsequence if one wants to reconstruct the subsequence itself.

How do you modify the LIS algorithm to allow **reconstruction** of the actual optimal subsequence? (no pseudocode)

Show LIS pseudocode for length only$\begin{array}{ll}\textsf{LIS(A[1..n])} & \\\quad \textsf{costruire il DAG G a partire da A} & \\\quad \texttt{for }\textsf{j := 1 }\texttt{to }\textsf{n }\texttt{do} & \\\quad\quad \textsf{L[j] := 1} & \\\quad \texttt{for }\textsf{j := 2 }\texttt{to }\textsf{n }\texttt{do} & \\\quad\quad \textsf{L[j] := }\max\limits_{(i,j) \in E} \{\textsf{L[i]}\} + 1 \quad \small\color{#777}{\textsf{// max su i #card
?
To reconstruct the elements of the optimal subsequence, an auxiliary array **`prev[1..n]`** is maintained:
`prev[j]` stores the index $i$ that maximized the value of $L[j]$ (that is, the predecessor node from which the longest path to $j$ comes).

**Reconstruction procedure:**

1. Identify the index $k$ that has the maximum value in $L[]$.
2. Trace back the chain of predecessors via `prev[k]` until encountering $0$ (or NIL).
3. The traversed elements are pushed onto a **Stack** and finally popped to yield the sequence in the correct order.
