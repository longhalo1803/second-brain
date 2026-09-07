---
title: "What are the fundamental conceptual differences between the Greedy technique and D..."
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
  - "What are the fundamental conceptual differences between the Greedy technique and D..."
---

# 🎴 What are the fundamental conceptual differences between the Greedy technique and D...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What are the fundamental conceptual differences between the **Greedy** technique and **Dynamic Programming** when tackling optimization problems? #card

?

- **GREEDY Algorithms:** construct the solution incrementally, making at each step a **locally optimal choice** that maximizes/minimizes the immediate partial cost, without ever reconsidering or modifying past choices.
- **DYNAMIC PROGRAMMING Algorithms:** are applied when one does not know a priori which subproblems need to be solved. They solve **ALL subproblems** (or compute them on demand by memoizing them) and **store their results in tables to reuse them** subsequently (caching) in solving larger problem instances.📌 Note:
  The term _Programming_ in this context does not refer to writing code (coding), but dates back to the 1950s (Bellman) in the sense of _planning_ or filling out a table.
