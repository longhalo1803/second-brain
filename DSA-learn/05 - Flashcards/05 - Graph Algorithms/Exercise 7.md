---
title: "Exercise 7"
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
  - "Exercise 7"
---

# 🎴 Exercise 7

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 Exercise 7

Rewrite the pseudocode of DFS for the cases where the graph is stored as an adjacency matrix and as adjacency lists.

_Hint_: Modify DFS so that the first time the exploration of an edge leads to an already visited node (`visited[v]=TRUE`), it returns True. In fact, such an edge can be removed without disconnecting the graph. If the visit finishes without finding such an edge, then return False. #card
?
**1. Graph stored as an Adjacency Matrix:**

```text
DFS(G)
    visited[0..n] new array
    for all u ∈ V do
        visited[u] := FALSE
    for all u ∈ V do
        if NOT visited[u] then
            DFS-Visit-Matrix(G, u)
```

```text
DFS-Visit-Matrix(G, u)
    visited[u] := TRUE
    for v := 1 to n do
        if G[u, v] = 1 AND NOT visited[v] then
            DFS-Visit-Matrix(G, v)
```

**2. Graph stored as Adjacency Lists:**

```text
DFS(G)
    visited[0..n] new array
    for all u ∈ V do
        visited[u] := FALSE
    for all u ∈ V do
        if NOT visited[u] then
            DFS-Visit-List(G, u)
```

```text
DFS-Visit-List(G, u)
    visited[u] := TRUE
    N := G[u]
    while N ≠q NIL do
        v := N.val
        if NOT visited[v] then
            DFS-Visit-List(G, v)
        N := N.next
```

📝 Examples of graph representation using an adjacency list:

⚠️ Warning:
`G` is an array whose index $x$ represents the source node (e.g., `G[1]` for node 1, `G[2]` for node 2).
`G[x]` does not contain the numerical value of node $x$, but rather a pointer to the head of the linked list containing all adjacent nodes (i.e., the targets of edges outgoing from $x$).
