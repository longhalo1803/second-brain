---
title: "Exercise 2 - LIS without DAG Construction"
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
  - "Exercise 2 - LIS without DAG Construction"
---

# 🎴 Exercise 2 - LIS without DAG Construction

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 Exercise 2 - LIS without DAG Construction

Write the pseudocode for a version of the dynamic programming algorithm for the Longest Increasing Subsequence (LIS) problem that does not explicitly construct the DAG, but instead, to determine the value $L[i]$, compares "brute force" the value at position $i$ of sequence $A$ with all elements preceding it in $A$.

Also compute the computational cost of this solution. #card
?
**Pseudocode:**

```text
LIS_NoDAG(A[1..n])
    for i := 1 to n do
        L[i] := 1                            // {#777}{// initialization}
    for i := 2 to n do
        for j := 1 to i - 1 do
            if A[j]  L[i] then
                [#2A80D4]{L[i] := L[j] + 1}          // {#D9534F}{≤ftarrow update max L[i]}
    return _{1 ≤ i ≤ n} L[i]
```

**Computational Cost:**

- **Time:** $\mathcal{O}(n^2)$ due to the two nested loops where for each element $A[i]$, $i-1$ comparisons are made with preceding elements: $\sum_{i=2}^n (i-1) = \frac{n(n-1)}{2} = \Theta(n^2)$.

- **Auxiliary space:** $\mathcal{O}(n)$ to store the values of array $L$.

📌 Note (with 🆚 without DAG):
The DAG-based method does not reduce the asymptotic complexity ($O(n^2)$ in the worst case), but reframes LIS as a Longest Path problem on a directed acyclic graph.
With a DAG, the condition $A[i] Version with DAG

```text
LIS(A[1..n])
    build DAG G from A
    for j := 1 to n do
        L[j] := 1
    for j := 2 to n do
        L[j] := _{(i,j) ∈ E} {L[i]} + 1
    return _{1 ≤ j ≤ n} L[j]
```
