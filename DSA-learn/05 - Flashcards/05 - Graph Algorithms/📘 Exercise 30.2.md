---
title: "📘 Exercise 30.2"
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
  - "📘 Exercise 30.2"
---

# 🎴 📘 Exercise 30.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📘 Exercise 30.2

**Input:** A directed graph $G = (V, E)$ with $V = \{1, \dots, n\}$ and two distinct vertices $s_1, s_2 \in V$.
**Output:** The number of vertices reachable from both $s_1$ and $s_2$ that are at the exact same shortest-path distance from $s_1$ and $s_2$.

- Show an example where the output is at least 2.
- Describe an algorithm in words and provide pseudocode.
- Analyze its computational complexity. #card
  ?
  **Reasoning:**
  Shortest-path distances in an unweighted directed graph can be computed using Breadth-First Search (BFS). By executing BFS independently from $s_1$ and $s_2$, we obtain two distance arrays, $dist_1$ and $dist_2$. A vertex $v$ satisfies the condition if it is reachable from both sources ($dist_1[v] \ne \infty \land dist_2[v] \ne \infty$) and $dist_1[v] = dist_2[v]$.

**1. Example:**
Let $V = \{1, 2, 3, 4, 5\}$, with $s_1 = 1$ and $s_2 = 2$.
Edges: $(1, 3), (2, 3), (1, 4), (2, 4), (3, 5)$.
Shortest distances:

- From $s_1 = 1$: $dist_1[3] = 1$, $dist_1[4] = 1$, $dist_1[5] = 2$.
- From $s_2 = 2$: $dist_2[3] = 1$, $dist_2[4] = 1$, $dist_2[5] = 2$.Vertices $3$, $4$, and $5$ are all at equal distance from both sources. Output: 3 (which is $\ge 2$).

**2. Algorithm Description:**
Initialize two distance arrays $dist_1$ and $dist_2$ of size $n$ with $\infty$. Run BFS from $s_1$ to populate $dist_1$, and run BFS from $s_2$ to populate $dist_2$. Then iterate through all vertices $v \in \{1, \dots, n\}$; if $dist_1[v] \ne \infty$ and $dist_1[v] = dist_2[v]$, increment a counter. Return the counter.

**Pseudocode:**

```text
Algorithm CountEquidistantNodes(G, s_1, s_2, n):
    dist_1 ≤ftarrow BFS_Distances(G, s_1, n)
    dist_2 ≤ftarrow BFS_Distances(G, s_2, n)
    count ≤ftarrow 0
    for v ≤ftarrow 1 to n do
        if dist_1[v] ≠ ∈fty dist_1[v] = dist_2[v] then
            count ≤ftarrow count + 1
    return count

Function BFS_Distances(G, src, n):
    dist[] ≤ftarrow array of size n initialized to ∈fty
    Q ≤ftarrow new_queue()
    dist[src] ≤ftarrow 0; \; enqueue(Q, src)
    while not is_empty(Q) do
        u ≤ftarrow dequeue(Q)
        for each v ∈ Adj[u] do
            if dist[v] = ∈fty then
                dist[v] ≤ftarrow dist[u] + 1
                enqueue(Q, v)
    return dist
```

**3. Complexity:**

- Time Complexity: Two BFS runs take $2 \times O(|V| + |E|) = O(|V| + |E|)$. The final loop takes $O(|V|)$. Total time is $O(|V| + |E|)$.
- Space Complexity: $O(|V|)$ auxiliary space for the distance arrays and BFS queue.
