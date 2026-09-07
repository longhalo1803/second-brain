---
title: "Exercise 13"
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
  - "Exercise 13"
---

# 🎴 Exercise 13

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 Exercise 13

The square of a directed graph $G = (V, E)$ is the graph $G^2 = (V, E^2)$ such that $(u, w) \in E^2$ if and only if $\exists v : (u, v) \in E \land (v, w) \in E$ (i.e., if there exists in $G$ a two-edge path between $u$ and $w$).
Write an algorithm that, given a graph $G$ represented by an adjacency matrix, returns the graph $G^2$. Compute the computational cost of the algorithm. #card
?
**Pseudocode:**

```text
Square(G)
    // Initialize G^2 as a new n n matrix
    for i := 1 to n do
        for j := 1 to n do
            found := FALSE
            k := 1
            while found = FALSE AND k ≤ n do
                if G[i, k] = 1 AND G[k, j] = 1 then
                    G^2[i, j] := 1
                    found := TRUE
                k := k + 1
            if found = FALSE then G^2[i, j] := 0
    return G^2
```

**Computational cost:**
The algorithm executes three nested loops (each running up to $n$ iterations), so the computational cost is $O(n^3)$.

**Notes:**
The algorithm also checks the cases $(i, i) - (i, j)$ and $(i, j) - (j, j)$, but the result will be correct because $\textsf{G}[i, i] = 0$ and $\textsf{G}[j, j] = 0$ (assuming no self-loops).
In the resulting graph $\textsf{G}^2$, the presence of a 1 on the diagonal does not indicate a self-loop but the presence in the original graph of a cycle of two edges (that is, in $G$ there are edges $(i, j)$ and $(j, i)$ so in $\textsf{G}^2$ we will have $\textsf{G}[i, i] = \textsf{G}[j, i] = 1$).
