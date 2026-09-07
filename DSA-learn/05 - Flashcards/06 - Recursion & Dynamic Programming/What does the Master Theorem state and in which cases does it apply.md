---
title: "What does the Master Theorem state and in which cases does it apply"
tags:
  - dsa
  - flashcards
  - clrs
  - dynamic-programming
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What does the Master Theorem state and in which cases does it apply"
---

# 🎴 What does the Master Theorem state and in which cases does it apply

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: What does the **Master Theorem** state and in which cases does it apply? #card

?
The Master Theorem is used to solve recurrence relations of the form:

$$
T(n) = \begin{cases} c_1 & \text{if } n = 1 \\ a \cdot T\left(\frac{n}{b}\right) + c_2 \cdot n^d & \text{otherwise} \end{cases}
$$

Where:

- $a \ge 1$: number of subproblems;
- $\frac{n}{b} > 1$: size of the problem ($n$ input size, $b>1$ division factor);
- $c_1 \ge 0, c_2 > 0$: constants for the base case and multiplicative constants;
- $d \ge 0$: polynomial order of the extra work (divide and combine operations) performed outside the recursive calls.

The theorem states that (note: $\log_b a = \frac{\log_2 a}{\log_2 b}$):

$$
T(n)\in
\begin{cases}
O(n^d) & \text{if } d > \log_b a \\[2pt]
O(n^{\log_b a}\log n) & \text{if } d = \log_b a \\[2pt]
O(n^{\log_b a}) & \text{if } d  \log_b a$ → the **additional work** performed at each level is larger than the recursion cost, so the term $O(n^d)$ dominates.
- $d = \log_b a$ → the **additional work and the recursion have the same weight**, so the cost accumulates across all levels and the factor $\log n$ appears.
- $d
$$
