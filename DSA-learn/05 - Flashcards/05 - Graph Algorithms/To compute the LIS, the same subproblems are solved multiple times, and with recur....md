---
title: "To compute the LIS, the same subproblems are solved multiple times, and with recur..."
tags:
  - dsa
  - flashcards
  - clrs
  - graphs
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "To compute the LIS, the same subproblems are solved multiple times, and with recur..."
---

# 🎴 To compute the LIS, the same subproblems are solved multiple times, and with recur...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: To compute the LIS, the same subproblems are solved multiple times, and with recursion the cost is too high, $O(2^n)$.

How do **Memoization** and **Iteration (Tabulation)** avoid the exponential explosion when computing the LIS? #card
?
**1. Memoization (Top-Down):**
The recursive structure is maintained, but the computed values of $L[j]$ are saved in a table so they don't have to be recomputed.
If the recursion requests a value already in the table, it is returned immediately without further recursive calls.

**2. Iteration / Tabulation (Bottom-Up):**
Since the graph is a DAG with edges directed only from smaller indices to larger indices ($i
