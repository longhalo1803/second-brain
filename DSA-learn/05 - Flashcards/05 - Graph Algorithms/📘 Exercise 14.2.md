---
title: "📘 Exercise 14.2"
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
  - "📘 Exercise 14.2"
---

# 🎴 📘 Exercise 14.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📘 Exercise 14.2

**Input:** A DAG $G = (V, E)$ with $V = \{1, \dots, n\}$ represented via adjacency lists.
**Output:** Print the identifiers of all sources of the graph (nodes with in-degree 0).

Provide pseudocode and analyze the computational complexity. #card
?
**Reasoning:**
A source has in-degree 0. We can compute the in-degree of all vertices by traversing all adjacency lists and tallying incoming edges.

**Algorithm Description:**
Initialize an array $in\_degree[1 \dots n]$ to 0. Traverse each vertex $u \in V$, and for each outgoing edge $(u, v) \in Adj[u]$, increment $in\_degree[v]$. In a second pass, iterate through $u \in \{1 \dots n\}$ and print every $u$ for which $in\_degree[u] = 0$.

**Pseudocode:**

```text
Algorithm PrintSources(G, n):
    in_degree[] ≤ftarrow array of size n initialized to 0
    for u ≤ftarrow 1 to n do
        for each v ∈ Adj[u] do
            in_degree[v] ≤ftarrow in_degree[v] + 1
    for u ≤ftarrow 1 to n do
        if in_degree[u] = 0 then
            print u
```

**Complexity:**

- Time Complexity: $\Theta(|V| + |E|)$, scanning each vertex and edge once.
- Space Complexity: $\Theta(|V|)$ for the in-degree array.
