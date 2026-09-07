---
title: "📘 Exercise 23.2"
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
  - "📘 Exercise 23.2"
---

# 🎴 📘 Exercise 23.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📘 Exercise 23.2

In a directed graph $G = (V, E)$, a node $v \in V$ is of _type Rome_ if every other vertex $w \in V$ can reach $v$ via a directed path.

- Show an example of a graph with a Rome node, and one without.
- Describe an algorithm and provide pseudocode that takes $G$ and $v$, and returns TRUE if $v$ is a Rome node, in $O(|V| + |E|)$ time. #card
  ?
  **Reasoning:**
  Every vertex $w$ can reach $v$ in $G$ if and only if $v$ can reach every vertex $w$ in the transpose graph $G^R$ (where every edge direction is reversed). Hence, running a BFS/DFS from $v$ on $G^R$ solves the problem in linear time.

**1. Examples:**

- _Has Rome node:_ $V=\{1, 2, 3\}$, edges $(1, 3), (2, 3)$. Node $3$ is reachable from $1$ and $2$. Thus $3$ is a Rome node.
- _No Rome node:_ Disconnected graph $V=\{1, 2\}$ with no edges.
  **2. Algorithm Description:**
  Construct the reversed graph $G^R = (V, E^R)$ in $O(|V| + |E|)$ time. Run BFS/DFS on $G^R$ starting at $v$. Count the number of reached vertices. If the count equals $|V|$, then $v$ can reach all nodes in $G^R$, which means all nodes can reach $v$ in $G$; return TRUE. Otherwise, return FALSE.

**Pseudocode:**

```text
Algorithm IsRomeNode(G, v):
    G^R ≤ftarrow TransposeGraph(G)
    visited[] ≤ftarrow array of false of size |V|
    Q ≤ftarrow new_queue(); \; enqueue(Q, v); \; visited[v] ≤ftarrow true
    reached ≤ftarrow 0
    while not is_empty(Q) do
        u ≤ftarrow dequeue(Q); \; reached ≤ftarrow reached + 1
        for each w ∈ G^R.Adj[u] do
            if not visited[w] then
                visited[w] ≤ftarrow true; \; enqueue(Q, w)
    return (reached = |V|)
```

**Complexity:**
Transposing and running BFS takes $O(|V| + |E|)$ time and $O(|V| + |E|)$ space.
