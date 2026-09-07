---
title: "📘 Exercise 32.2"
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "📘 Exercise 32.2"
---

# 🎴 📘 Exercise 32.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 32.2

An undirected graph $G$ is _2-colorable_ if each vertex can be colored Red or White such that no two adjacent vertices share the same color.

**Input:** An undirected graph $G = (V, E)$ with $V = \{1, \dots, n\}$.
**Output:** TRUE if $G$ is 2-colorable, FALSE otherwise.

- Show an example of a 2-colorable graph and an example of a non-2-colorable graph.
- Describe an algorithm in words and provide pseudocode.
- Prove the correctness of the algorithm.
- Analyze its computational complexity.
- Would the algorithm work if the input graph were directed? #card
  ?
  **Reasoning:**
  A graph is 2-colorable if and only if it is bipartite, which holds if and only if the graph contains no odd-length cycles. We can test bipartiteness using BFS (or DFS) by assigning alternating colors to successive BFS levels.

**1. Examples:**

- _2-Colorable:_ Cycle $C_4$ with edges $(1, 2), (2, 3), (3, 4), (4, 1)$. Vertices $1, 3$ are Red; vertices $2, 4$ are White. Valid.
- _Non-2-Colorable:_ Triangle $C_3$ with edges $(1, 2), (2, 3), (3, 1)$. An odd cycle requires at least 3 colors. Invalid.
  **2. Algorithm Description:**
  Maintain an array $color$ initialized to $\text{UNCOLORED}$ for all vertices. Iterate over all vertices to handle disconnected components. When an uncolored vertex $s$ is found, color it Red and start a BFS. For each dequeued vertex $u$, inspect each neighbor $v \in Adj[u]$: if $v$ is uncolored, assign it the opposite color of $u$ and enqueue it; if $v$ already has the same color as $u$, an odd cycle is detected, so return FALSE. If all components are successfully colored, return TRUE.

**Pseudocode:**

```text
Algorithm IsTwoColorable(G, n):
    color[] ≤ftarrow array of size n initialized to UNCOLORED
    Q ≤ftarrow new_queue()
    for i ≤ftarrow 1 to n do
        if color[i] = UNCOLORED then
            color[i] ≤ftarrow RED
            enqueue(Q, i)
            while not is_empty(Q) do
                u ≤ftarrow dequeue(Q)
                for each v ∈ Adj[u] do
                    if color[v] = color[u] then return FALSE
                    if color[v] = UNCOLORED then
                        color[v] ≤ftarrow (color[u] = RED \,?\, WHITE : RED)
                        enqueue(Q, v)
    return TRUE
```

**3. Proof of Correctness:**
BFS partitions vertices into layers based on shortest distance from the source. In an undirected graph, every edge connects vertices either within the same layer or in adjacent layers. If an edge connects two vertices in the same layer, they receive the same color, producing an odd cycle of length $2d + 1$, correctly causing the algorithm to return FALSE. If no intra-layer edges exist, all edges connect adjacent layers which receive opposite colors, yielding a valid 2-coloring.

**4. Complexity:**
Every vertex and edge is examined a constant number of times: $\Theta(|V| + |E|)$ time and $\Theta(|V|)$ auxiliary space.

**5. Directed Graph Case:**
In standard graph theory, 2-colorability of a directed graph refers to the 2-colorability of its underlying undirected graph (weakly connected components). If the BFS strictly follows directed edges, it will fail to traverse incoming edges, missing potential color conflicts and odd cycles in the underlying structure. Thus, it only works if edges are traversed irrespective of their directed orientation.
