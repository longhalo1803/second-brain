---
title: "State the Longest Increasing Subsequence problem and present the associated dynami..."
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
  - "State the Longest Increasing Subsequence problem and present the associated dynami..."
---

# 🎴 State the Longest Increasing Subsequence problem and present the associated dynami...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: ❓ State the Longest Increasing Subsequence problem and present the associated dynamic programming algorithm (pseudocode is not strictly required, pseudocode alone without explanations is not sufficient). Explain how solutions to smaller subproblems are used to build the solution to a larger subproblem in this algorithm. #card

?

- **Problem Statement (LIS):**
  Given a sequence of $n$ numbers $A[1 \dots n]$, an increasing subsequence is a subfamily of indices $i_1 < i_2 < \dots < i_k$ such that $A[i_1] < A[i_2] < \dots < A[i_k]$. The problem consists of finding the maximum length $k$ among all possible strictly increasing subsequences.
- **Dynamic Programming Algorithm:**
- **Subproblem definition:** Let $L[i]$ be the length of the longest increasing subsequence that **must end** with element $A[i]$.
- **Recurrence relation:**
  A subsequence ending at $A[i]$ can be formed by extending any valid increasing subsequence ending at an earlier element $A[j]$ (with $j < i$), provided that $A[j] < A[i]$. If no such preceding smaller element exists, the subsequence consists solely of element $A[i]$ (length $1$).

$$

L[i] = 1 + \max(\{0\} \cup \{L[j] \mid 1 \le j < i \text{ and } A[j] < A[i]\})

$$

- The solution to the overall problem will be given by the maximum across all possible endpoints:

$$

\text{LIS} = \max\_{1 \le i \le n} L[i]

$$

- **Use of smaller subproblem solutions:**
  The algorithm computes vector $L[1 \dots n]$ in increasing order of index from $i = 1$ to $n$. When solving subproblem $L[i]$, all optimal solutions $L[j]$ for $j < i$ have already been stored in a table (_memoization_ or _bottom-up_ approach). The algorithm does not recompute the history of preceding paths recursively; instead, it directly queries the cells $L[j]$ of eligible predecessors ($A[j] < A[i]$), selects the maximum value among them, and adds $1$. The time cost of the algorithm is $\mathcal{O}(n^2)$.
