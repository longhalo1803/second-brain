---
title: "📘 Exercise 15.2"
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
  - "📘 Exercise 15.2"
---

# 🎴 📘 Exercise 15.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📘 Exercise 15.2

**Input:** A directed graph $G = (V, E)$ with $V = \{1, \dots, n\}$, a node $v \in V$, and an integer $k$ such that $0 < k < n$.
**Output:** Print all identifiers of nodes at shortest-path distance exactly $k$ from $v$.

Choose graph representation, explain the algorithm, provide pseudocode, and analyze computational complexity. #card
?
**Reasoning:**
In an unweighted graph, Breadth-First Search (BFS) explores vertices in order of increasing distance from the source. Running BFS from $v$ discovers shortest path distances to all reachable nodes.

**Algorithm Description:**
Represent $G$ via adjacency lists. Run BFS from $v$, maintaining an array $dist$ initialized to $\infty$, with $dist[v] \leftarrow 0$. When a vertex $u$ at distance $k$ is dequeued, print it. Since BFS explores vertices in non-decreasing order of distance, once vertices at distance $> k$ are reached, the search can stop.

**Pseudocode:**

```text
Algorithm PrintNodesAtDistanceK(G, v, k):
    dist[] ≤ftarrow array of size |V| initialized to ∈fty
    Q ≤ftarrow new_queue(); \; enqueue(Q, v); \; dist[v] ≤ftarrow 0
    while not is_empty(Q) do
        u ≤ftarrow dequeue(Q)
        if dist[u] = k then
            print u
        if dist[u] < k then
            for each w ∈ Adj[u] do
                if dist[w] = ∈fty then
                    dist[w] ≤ftarrow dist[u] + 1
                    enqueue(Q, w)
```

**Complexity:**

- Time Complexity: $O(|V| + |E|)$ using adjacency lists.
- Space Complexity: $O(|V|)$ for the distance array and BFS queue.
