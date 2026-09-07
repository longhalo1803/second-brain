---
title: "Exercise 1 Write the pseudocode of a DFS-based algorithm that, given an undirected..."
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
  - "Exercise 1 Write the pseudocode of a DFS-based algorithm that, given an undirected..."
---

# 🎴 Exercise 1 Write the pseudocode of a DFS-based algorithm that, given an undirected...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Exercise 1: Write the pseudocode of a DFS-based algorithm that, given an undirected graph $G=(V,E)$ as input, determines whether the graph is **connected** (returning `TRUE` or `FALSE`).

💡 HintAn undirected graph is connected if a single DFS traversal started from any arbitrary source node (e.g., node 1) manages to reach and visit all nodes in $V$. #card
?
The algorithm performs a single call to `DFS-Visit` starting from an arbitrary source node (for example node 1). Afterwards, it checks whether all nodes are marked as visited.

```text
IsConnected(G)
    visited[0..n] new array
    for all v ∈ V do
        visited[v] := FALSE
    DFS-Visit(G, 1)                      // traversal starting from node 1
    for all v ∈ V do
        if visited[v] = FALSE then
            return FALSE                         // at least one node was not reached
    return TRUE                          // all nodes have been visited

DFS-Visit(G, v)
    visited[v] := TRUE
    for all (v, u) ∈ E do
        if visited[u] = FALSE then
            DFS-Visit(G, u)
```

**Computational cost:** $O(|V| + |E|)$.
