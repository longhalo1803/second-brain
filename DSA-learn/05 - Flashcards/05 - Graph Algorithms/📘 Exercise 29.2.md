---
title: "📘 Exercise 29.2"
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
  - "📘 Exercise 29.2"
---

# 🎴 📘 Exercise 29.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📘 Exercise 29.2

Let $G = (V, E)$ be an undirected graph with $k > 1$ connected components, with $V = \{1, \dots, n\}$.
Make $G$ connected by adding exactly $k - 1$ edges using procedure `AddEdge(u, v)` (cost $O(1)$). The value $k$ is unknown upfront.

- Show an example with at least 10 nodes before and after adding edges.
- Describe the algorithm in words and provide pseudocode.
- Argue correctness and analyze computational complexity. #card
  ?
  **Reasoning:**
  Run BFS or DFS to identify all connected components. Record one representative vertex from each component. Connecting these representatives in a chain adds exactly $k - 1$ edges and connects the graph.

**Algorithm & Pseudocode:**

```text
Algorithm ConnectGraph(G, n):
    visited[] ≤ftarrow array of false of size n
    reps ≤ftarrow new empty list
    for i ≤ftarrow 1 to n do
        if not visited[i] then
            reps.append(i)
            BFS_Mark(G, i, visited)
    for j ≤ftarrow 0 to |reps| - 2 do
        AddEdge(reps[j], reps[j+1])
```

**Complexity:**
BFS visits every vertex and edge once: $\Theta(|V| + |E|)$ time and $\Theta(|V|)$ space.
