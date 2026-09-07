---
title: "What are the four fundamental general principles for designing and applying Dynami..."
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
  - "What are the four fundamental general principles for designing and applying Dynami..."
---

# 🎴 What are the four fundamental general principles for designing and applying Dynami...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What are the four fundamental general principles for designing and applying Dynamic Programming? #card

?

- **Storing optimal solutions to subproblems:** The values of optimal solutions to subproblems (e.g., values in $L[1..n]$) are stored in order to reuse them whenever needed.
- **Storing choices for reconstruction:** The choices that led to the optimal solutions of subproblems (e.g., values in the array $prev[1..n]$) are stored, allowing backward reconstruction of the global optimal solution.
- **Order of resolution by increasing size:** A clear dependency order is established to solve the subproblems based on their size (e.g., the order of indices of the sequence or topological order in the DAG).
- **Identifying Base Cases:** The solutions to the smallest subproblems for which no further subdivision is possible are determined (e.g., DAG nodes with no incoming edges, for which $L[j] = 1$ and $prev[j] = \text{NIL}$).
