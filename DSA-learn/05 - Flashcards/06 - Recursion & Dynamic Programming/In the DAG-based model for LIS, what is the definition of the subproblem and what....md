---
title: "In the DAG-based model for LIS, what is the definition of the subproblem and what..."
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
  - "In the DAG-based model for LIS, what is the definition of the subproblem and what..."
---

# 🎴 In the DAG-based model for LIS, what is the definition of the subproblem and what...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: In the DAG-based model for LIS, what is the definition of the **subproblem** and what is the **recurrence equation**? #card

?
**Definition of the subproblem $L[j]$:**
$L[j]$ = length of the longest increasing subsequence (i.e., the longest path in the DAG) that **ends exactly at node $j$** (corresponding to element $a_j$).

**Recurrence equation:**

$$

L[j] = \max\_{(i,j) \in E} \{ L[i] \} + 1

$$

that is, considering the previous elements $i k-1
