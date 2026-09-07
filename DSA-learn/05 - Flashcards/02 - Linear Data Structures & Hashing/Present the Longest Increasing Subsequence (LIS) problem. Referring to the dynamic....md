---
title: "Present the Longest Increasing Subsequence (LIS) problem. Referring to the dynamic..."
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
  - "Present the Longest Increasing Subsequence (LIS) problem. Referring to the dynamic..."
---

# 🎴 Present the Longest Increasing Subsequence (LIS) problem. Referring to the dynamic...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: ❓ Present the Longest Increasing Subsequence (LIS) problem. Referring to the dynamic programming algorithm seen previously to solve the problem, define the subproblem, write the equation for computing the value at a generic index $i$ of array $L$, and explain its meaning. What is the computational cost of the algorithm? What would be the cost of a brute-force approach? #card

?

- **Problem Definition and Subproblem:**
  Given a sequence $A[1 \dots n]$, the LIS is the longest subsequence whose elements appear in strictly increasing order.
- **Subproblem:** Define $L[i]$ as the length of the longest increasing subsequence restricted to prefix $A[1 \dots i]$ that **must end with element $A[i]$**.
- **Recurrence Equation:**

$$

L[i] = 1 + \max(\{0\} \cup \{L[j] \mid 1 \le j < i \text{ with } A[j] < A[i]\})

$$

_Explanation:_ Element $A[i]$ can extend any preceding increasing subsequence that ends at an element $A[j]$ smaller than $A[i]$ ($A[j] < A[i]$). To maximize the total length, look among all valid predecessors $j$ for the one with maximum $L[j]$. The $+1$ term accounts for the inclusion of $A[i]$ itself in the subsequence. If no such $A[j] < A[i]$ exists, the $\max$ term yields $0$ and $L[i] = 1$.
The final result of the problem is $\max_{1 \le i \le n} L[i]$.

- **Computational Cost:**
- **Dynamic Programming:** For each cell $i$ from $1$ to $n$, all $j < i$ are checked, performing $i-1$ comparisons. The total number of operations is $\sum_{i=1}^{n} (i-1) = \frac{n(n-1)}{2}$, leading to a time cost of $\mathcal{O}(n^2)$ and space $\mathcal{O}(n)$ for array $L$.
- **Brute Force:** The brute-force approach generates all possible subsets of the $n$-element array (there are $2^n$ of them), checks each to see if it is strictly increasing (cost $\mathcal{O}(n)$), and picks the longest one. The overall cost would thus be $\mathcal{O}(n \cdot 2^n)$, which is highly exponential and intractable.
