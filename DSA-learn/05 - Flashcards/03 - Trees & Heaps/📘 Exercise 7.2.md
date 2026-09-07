---
title: "📘 Exercise 7.2"
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
  - "📘 Exercise 7.2"
---

# 🎴 📘 Exercise 7.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 7.2

**Input:** Graph $G = (V, E)$, positive node weights $w : V \to \mathbb{N}$, nodes $x, y \in V$, and integer threshold $k \in \mathbb{N}$.
**Output:** TRUE if there is a path in $G$ from $x$ to $y$ passing only through nodes of weight $\le k$, FALSE otherwise.

Describe the algorithm in words, write high-level pseudocode, and analyze its computational complexity. #card
?
**Reasoning:**
A path is valid if and only if all its nodes have weight $\le k$. Nodes with weight $> k$ cannot be used. We can run a graph traversal (BFS or DFS) starting from $x$, ignoring any node with weight $> k$.

**Algorithm Description:**
If $w(x) > k$ or $w(y) > k$, return FALSE immediately. Otherwise, initialize a visited array. Start BFS or DFS from $x$. When inspecting neighbors of the current vertex, only visit unvisited neighbors whose weight is $\le k$. If $y$ is reached, return TRUE. If the traversal completes without reaching $y$, return FALSE.

**Pseudocode:**

```text
Algorithm ValidPath(G, w, x, y, k):
    if w(x) > k w(y) > k then return FALSE
    visited[] ≤ftarrow array of false of size |V|
    Q ≤ftarrow new_queue(); \; enqueue(Q, x); \; visited[x] ≤ftarrow true
    while not is_empty(Q) do
        u ≤ftarrow dequeue(Q)
        if u = y then return TRUE
        for each v ∈ Adj[u] do
            if not visited[v] w(v) ≤ k then
                visited[v] ≤ftarrow true; \; enqueue(Q, v)
    return FALSE
```

**Complexity:**

- Time Complexity: $O(|V| + |E|)$, since each valid node and edge is examined at most once.
- Space Complexity: $O(|V|)$ for the visited array and queue.
