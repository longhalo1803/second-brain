---
title: "In order for a Dynamic Programming algorithm to have polynomial computational cost..."
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
  - "In order for a Dynamic Programming algorithm to have polynomial computational cost..."
---

# 🎴 In order for a Dynamic Programming algorithm to have polynomial computational cost...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: In order for a Dynamic Programming algorithm to have **polynomial** computational cost, which two conditions must be satisfied? #card

?
For complexity to be polynomial, it is necessary that:

1. The **number of distinct subproblems** to solve is polynomial.
2. The **time to combine** the solutions of the subproblems (to obtain the solution of the larger problem) is polynomial.

📌 Note:
Solutions to subproblems are stored in a data structure (e.g., table/matrix), avoiding recomputing them multiple times even without knowing a priori which ones will be strictly necessary.
