---
title: "What is the pseudocode of the LIS(A) algorithm to compute only the length of the l..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the pseudocode of the LIS(A) algorithm to compute only the length of the l..."
---

# 🎴 What is the pseudocode of the LIS(A) algorithm to compute only the length of the l...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: 🟢 What is the **pseudocode** of the `LIS(A)` algorithm to compute only the **length** of the longest increasing subsequence? #card

?

```text
LIS(A[1..n])
    construct the DAG G from A
    for j := 1 to n do
        L[j] := 1
    for j := 2 to n do
        L[j] := _{(i,j) ∈ E} {L[i]} + 1      // {#777}{// max over i
```
