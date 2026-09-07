---
title: "📘 Exercise 20.2"
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
  - "📘 Exercise 20.2"
---

# 🎴 📘 Exercise 20.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 20.2

**Input:** A directed graph $G = (V, E)$ and three distinct vertices $u, v, w \in V$.
**Output:** TRUE if there exists a directed path from $u$ to $v$ passing through $w$, FALSE otherwise.

- Describe the algorithm in words and provide pseudocode.
- Analyze its computational complexity. #card
  ?
  **Reasoning:**
  A directed path from $u$ to $v$ passing through $w$ exists if and only if there exists a path from $u$ to $w$ AND a path from $w$ to $v$. These two reachability queries can be independently determined using two BFS (or DFS) traversals.

**Algorithm Description:**
Run a BFS/DFS starting at $u$. If $w$ is not reachable, return FALSE. Otherwise, run a second BFS/DFS starting at $w$. If $v$ is reachable from $w$, return TRUE; otherwise, return FALSE.

**Pseudocode:**

```text
Algorithm PathThroughW(G, u, v, w):
    if not IsReachable(G, u, w) then return FALSE
    if not IsReachable(G, w, v) then return FALSE
    return TRUE

Function IsReachable(G, src, dest):
    visited[] ≤ftarrow array of false; \; Q ≤ftarrow new_queue()
    enqueue(Q, src); \; visited[src] ≤ftarrow true
    while not is_empty(Q) do
        curr ≤ftarrow dequeue(Q)
        if curr = dest then return TRUE
        for each neighbor ∈ Adj[curr] do
            if not visited[neighbor] then
                visited[neighbor] ≤ftarrow true; \; enqueue(Q, neighbor)
    return FALSE
```

**Complexity:**
Two BFS passes take $2 \times O(|V| + |E|) = O(|V| + |E|)$ time and $O(|V|)$ auxiliary space.
