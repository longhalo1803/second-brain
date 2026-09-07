---
title: "📘 Exercise 12.1"
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
  - "📘 Exercise 12.1"
---

# 🎴 📘 Exercise 12.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 12.1

A _sink_ in a directed graph is a vertex with out-degree 0.

**Input:** A Directed Acyclic Graph (DAG) $G = (V, E)$ and a source vertex $s \in V$.
**Output:** The number of distinct sink vertices reachable from $s$.

- Provide an example with a DAG of at least 8 nodes, showing input and output.
- Describe an algorithm in words and provide pseudocode.
- Analyze its computational complexity in time and space. #card
  ?
  **Reasoning:**
  We traverse the graph starting from $s$ using BFS or DFS. A vertex is counted if it is reached by the traversal and its out-degree is 0 (i.e. its adjacency list is empty).

**1. Example:**
Let $V = \{1, 2, 3, 4, 5, 6, 7, 8\}$ and edges be $(1, 2), (1, 3), (2, 4), (3, 5), (4, 6), (5, 6), (5, 7), (7, 8)$.
Let $s = 1$. Vertices with out-degree 0 are $6$ and $8$. Both are reachable from $1$. Output: 2.

**2. Algorithm Description:**
Initialize a boolean array $visited$ to false and a counter $count \leftarrow 0$. Run BFS starting at $s$. Whenever a vertex $u$ is dequeued, check if $Adj[u]$ is empty; if so, increment $count$. For each unvisited neighbor $v \in Adj[u]$, mark $visited[v] \leftarrow \text{true}$ and enqueue $v$. Return $count$.

**3. Pseudocode:**

```text
Algorithm CountReachableSinks(G, s):
    visited[] ≤ftarrow array of false of size |V|
    Q ≤ftarrow new_queue(); \; enqueue(Q, s); \; visited[s] ≤ftarrow true
    count ≤ftarrow 0
    while not is_empty(Q) do
        u ≤ftarrow dequeue(Q)
        if |Adj[u]| = 0 then
            count ≤ftarrow count + 1
        for each v ∈ Adj[u] do
            if not visited[v] then
                visited[v] ≤ftarrow true; \; enqueue(Q, v)
    return count
```

**4. Complexity:**

- Time Complexity: $O(|V| + |E|)$, as each reachable vertex and edge is processed once.
- Space Complexity: $O(|V|)$ for the queue and visited array.
