---
title: "What is the computational complexity of Algorithm 2 (DFS-TS) for topological sorting"
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
  - "What is the computational complexity of Algorithm 2 (DFS-TS) for topological sorting"
---

# 🎴 What is the computational complexity of Algorithm 2 (DFS-TS) for topological sorting

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the computational complexity of Algorithm 2 (DFS-TS) for topological sorting?

````text
TopologicalSort(G)                   // Main procedure
    {#00C800}{visited[0..n]} new array
    S := new_stack()
    for all v ∈ V do
        {#00C800}{visited[v] := FALSE}
    for all v ∈ V do
        if {#00C800}{visited[v] = FALSE} then
            DFS-TS(G, v)
    return S

DFS-TS(G, v)
    {#00C800}{visited[v] := TRUE}
    for all (v,u) ∈ E do                 // edges outgoing from v
        if {#00C800}{visited[u] = FALSE} then
            DFS-TS(G, u)
    push(S, v)
``` #card
?
The computational cost of Algorithm 2 is **$O(|V| + |E|)$**.

The algorithm executes a standard depth-first search (DFS) on the graph.

- Each node $v \in V$ is visited only once (thanks to the `visited` array).
- Each outgoing edge $(v, u) \in E$ is examined exactly once.
- The additional operation `push(S, v)` performed at the end of recursion takes constant time $O(1)$.Therefore, the total running time is linearly proportional to the number of nodes and edges in the graph, which is $O(|V| + |E|)$.
````
