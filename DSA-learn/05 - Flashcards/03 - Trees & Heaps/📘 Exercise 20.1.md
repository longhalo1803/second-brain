---
title: "📘 Exercise 20.1"
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "📘 Exercise 20.1"
---

# 🎴 📘 Exercise 20.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 20.1

**Input:** A DAG $G = (V, E)$ represented by an adjacency matrix $M[1 \dots n, 1 \dots n]$.
**Output:** TRUE if the DAG is a full binary tree (where every node has 0 or 2 children and edges are directed from parent to children), FALSE otherwise.

- Describe the algorithm in words and provide pseudocode.
- Argue correctness.
- Explain modifications to return the number of full binary trees if $G$ is a forest of full binary trees. #card
  ?
  **Reasoning:**
  A directed tree has: (1) exactly one root with in-degree 0; (2) every other node has in-degree exactly 1; (3) out-degree of every node is either 0 or 2; (4) exactly $n - 1$ edges; (5) all vertices are reachable from the root (ensuring weak connectivity).

**Algorithm & Pseudocode:**

```text
Algorithm IsFullBinaryTree(M, n):
    in_deg[] ≤ftarrow array of 0; \; out_deg[] ≤ftarrow array of 0
    for i ≤ftarrow 1 to n do
        for j ≤ftarrow 1 to n do
            if M[i][j] = 1 then
                out_deg[i] ≤ftarrow out_deg[i] + 1; \; in_deg[j] ≤ftarrow in_deg[j] + 1
    root ≤ftarrow -1
    for i ≤ftarrow 1 to n do
        if out_deg[i] ≠ 0 out_deg[i] ≠ 2 then return FALSE
        if in_deg[i] = 0 then
            if root ≠ -1 then return FALSE
            root ≤ftarrow i
        else if in_deg[i] ≠ 1 then return FALSE
    if root = -1 then return FALSE
    return (ReachableCount(M, root, n) = n)
```

**Complexity:**
$\Theta(n^2)$ time to parse the matrix, and $O(n)$ space.

**Forest Modification:**
Count vertices with in-degree 0 as $k$. Ensure all other vertices have in-degree 1, and all vertices have out-degree $\in \{0, 2\}$. Verify that total edges $= n - k$. If valid, return $k$; otherwise, return 0.
