---
title: "📘 Exercise 8.1"
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
  - "📘 Exercise 8.1"
---

# 🎴 📘 Exercise 8.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📘 Exercise 8.1

Let $G = (V, E)$ be a connected undirected graph representing a road network and let $u, v, w \in V$ be three vertices where three friends reside. The friends wish to meet at a vertex $z \in V$ that minimizes the total distance traveled, defined as $\text{dist}(u, z) + \text{dist}(v, z) + \text{dist}(w, z)$.

Describe an algorithm in words and provide pseudocode that takes $G, u, v, w$ and returns $z$. Analyze its computational complexity. #card
?
**Reasoning:**
Since the edge weights are uniform (number of edges), shortest paths from a single source are computed via BFS. Running BFS independently from $u$, $v$, and $w$ yields three distance arrays $d_u, d_v, d_w$. Summing these for each candidate vertex $z \in V$ identifies the optimal meeting point.

**Algorithm Description:**
Run BFS from $u$ to compute distance array $D_u$, from $v$ to compute $D_v$, and from $w$ to compute $D_w$. Then iterate through all vertices $i \in V$ to find the vertex $z$ that minimizes $D_u[i] + D_v[i] + D_w[i]$.

**Pseudocode:**

```text
Algorithm OptimalMeetingNode(G, u, v, w):
    D_u ≤ftarrow BFS_Distance(G, u)
    D_v ≤ftarrow BFS_Distance(G, v)
    D_w ≤ftarrow BFS_Distance(G, w)
    best_z ≤ftarrow u, \; min_total ≤ftarrow ∈fty
    for each i ∈ V do
        total_dist ≤ftarrow D_u[i] + D_v[i] + D_w[i]
        if total_dist < min_total then
            min_total ≤ftarrow total_dist
            best_z ≤ftarrow i
    return best_z
```

**Complexity:**

- Time Complexity: 3 BFS executions cost $3 \times O(|V| + |E|) = O(|V| + |E|)$. The final minimum scan takes $O(|V|)$. Total time is $O(|V| + |E|)$.
- Space Complexity: $O(|V|)$ to store the three distance arrays.
