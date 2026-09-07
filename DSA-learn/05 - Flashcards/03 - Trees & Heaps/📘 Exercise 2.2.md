---
title: "📘 Exercise 2.2"
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
  - "📘 Exercise 2.2"
---

# 🎴 📘 Exercise 2.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 2.2

Let $G = (V, E)$ be a connected undirected graph. The distance between $u, v \in V$ is the number of edges on the shortest path between them. The diameter of $G$ is $\max_{u, v \in V} \text{dist}(u, v)$.

- Provide an example of a graph with at least 5 nodes and at least 8 edges, state its diameter, and indicate the path determining it.
- Explain why DFS is not suitable for computing the diameter of $G$.
- Describe and provide pseudocode of an algorithm to compute the diameter of connected undirected graph $G=(V,E)$ with $V = \{1, \dots, n\}$.
- Analyze the computational complexity. #card
  ?
  **Reasoning:**
  The diameter is the maximum shortest-path distance over all pairs of vertices. In unweighted graphs, BFS from a single vertex determines single-source shortest path distances. Running BFS from every vertex gives all-pairs shortest paths.

**1. Example:**
Let $V = \{1, 2, 3, 4, 5\}$. Form a complete graph $K_4$ on $\{1, 2, 3, 4\}$ (6 edges), and add edges $(3, 5)$ and $(4, 5)$ (total 8 edges). The shortest distance between $1$ and $5$ is 2 (e.g. path $\langle 1, 4, 5 \rangle$). Every other pair has distance 1 or 2. The diameter is 2.

**2. Why DFS is Unsuitable:**
DFS explores paths deeply before backtracking and does not compute shortest paths in unweighted graphs. Path lengths in a DFS tree generally exceed geodesic distances.

**3. Pseudocode:**

```text
Algorithm GraphDiameter(G):
    max_diam ≤ftarrow 0
    for each s ∈ V do
        dist[] ≤ftarrow array of size |V| initialized to ∈fty
        Q ≤ftarrow new_queue(); \; enqueue(Q, s); \; dist[s] ≤ftarrow 0
        while not is_empty(Q) do
            u ≤ftarrow dequeue(Q)
            max_diam ≤ftarrow (max_diam, dist[u])
            for each v ∈ Adj[u] do
                if dist[v] = ∈fty then
                    dist[v] ≤ftarrow dist[u] + 1; \; enqueue(Q, v)
    return max_diam
```

**4. Complexity:**

- Time Complexity: BFS from one vertex takes $O(|V| + |E|)$. Repeating for all $|V|$ vertices takes $O(|V|(|V| + |E|))$.
- Space Complexity: $O(|V|)$ for the queue and distance array.
