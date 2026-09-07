---
title: "📘 Exercise 22.2"
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
  - "📘 Exercise 22.2"
---

# 🎴 📘 Exercise 22.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📘 Exercise 22.2

A _triangle_ in an undirected graph $G=(V,E)$ with $V = \{1, \dots, n\}$ is a set of 3 distinct vertices $\{x, y, z\}$ such that $(x,y), (y,z), (z,x) \in E$.

- For a complete graph with 10 nodes, list all triangles composed exclusively of odd-labeled nodes.
- Describe and provide pseudocode of an algorithm to count all triangles composed solely of odd-labeled nodes in a graph represented by an adjacency matrix.
- Analyze computational complexity.
- In general, how many such triangles exist in a complete graph with $n$ nodes? What is the minimum $n$ for at least one such triangle to exist? #card
  ?
  **Reasoning:**
  Filter the vertices to odd identifiers: $O_{odd} = \{1, 3, 5, \dots\}$. Check all triplets $\{i, j, k\} \subseteq O_{odd}$ with $i < j < k$ for mutual edges using the adjacency matrix.

**1. Example:**
Odd nodes in $K_{10}$ are $\{1, 3, 5, 7, 9\}$ ($5$ nodes). All $\binom{5}{3} = 10$ triplets form triangles: $\{1,3,5\}, \{1,3,7\}, \{1,3,9\}, \{1,5,7\}, \{1,5,9\}, \{1,7,9\}, \{3,5,7\}, \{3,5,9\}, \{3,7,9\}, \{5,7,9\}$.

**2. Pseudocode:**

```text
Algorithm CountOddTriangles(M, n):
    count ≤ftarrow 0
    for i ≤ftarrow 1 to n step 2 do
        for j ≤ftarrow i + 2 to n step 2 do
            if M[i][j] = 1 then
                for k ≤ftarrow j + 2 to n step 2 do
                    if M[i][k] = 1 M[j][k] = 1 then
                        count ≤ftarrow count + 1
    return count
```

**3. Complexity:**
There are $m = \lceil n/2 \rceil$ odd vertices. The triple loop takes $\binom{m}{3} = O(n^3)$ time and $O(1)$ space.

**4. General Formula:**
In a complete graph, every triplet of odd nodes forms a triangle. Number of triangles is $\binom{\lceil n/2 \rceil}{3}$. At least one triangle requires $\lceil n/2 \rceil \ge 3 \implies n \ge 5$.
