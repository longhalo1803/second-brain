---
title: "What is the complete pseudocode of the LIS algorithm using the prev array and a st..."
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
  - "What is the complete pseudocode of the LIS algorithm using the prev array and a st..."
---

# 🎴 What is the complete pseudocode of the LIS algorithm using the prev array and a st...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 🟢 What is the **complete pseudocode** of the LIS algorithm using the `prev` array and a stack to reconstruct the subsequence?

Show LIS pseudocode for length only$\begin{array}{ll}\textsf{LIS(A[1..n])} & \\\quad \textsf{costruire il DAG G a partire da A} & \\\quad \texttt{for }\textsf{j := 1 }\texttt{to }\textsf{n }\texttt{do} & \\\quad\quad \textsf{L[j] := 1} & \\\quad \texttt{for }\textsf{j := 2 }\texttt{to }\textsf{n }\texttt{do} & \\\quad\quad \textsf{L[j] := }\max\limits_{(i,j) \in E} \{\textsf{L[i]}\} + 1 \quad \small\color{#777}{\textsf{// max su i #card
?

```text
LIS(A[1..n])
    construct the DAG G from A
    for j := 1 to n do
        {#29B6F6}{L[j] := 1}
        {#A040A0}{prev[j] := 0}
    for j := 2 to n do
        {#29B6F6}{L[j] := _{(i,j) ∈ E} {L[i]} + 1}
        {#A040A0}{prev[j] := index i that maximized L[j]}
    {#2E7D32}{lis := new_stack()}
    k := index of the maximum value in L[]
    while k > 0 do
        {#2E7D32}{push(lis, A[k])}
        {#A040A0}{k := prev[k]}
    return lis
```
