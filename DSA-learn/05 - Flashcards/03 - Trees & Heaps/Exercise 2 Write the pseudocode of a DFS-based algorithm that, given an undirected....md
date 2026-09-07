---
title: "Exercise 2 Write the pseudocode of a DFS-based algorithm that, given an undirected..."
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
  - "Exercise 2 Write the pseudocode of a DFS-based algorithm that, given an undirected..."
---

# 🎴 Exercise 2 Write the pseudocode of a DFS-based algorithm that, given an undirected...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Exercise 2: Write the pseudocode of a DFS-based algorithm that, given an undirected graph $G=(V,E)$ as input, computes and returns the **total number of connected components** of $G$.

💡 HintAll nodes reachable by a DFS traversal started from a given node belong to the same connected component. If there are unvisited nodes, start a new DFS while incrementing a counter $c$. #card
?
A counter $c$ initialized to 0 is maintained. Each time an unvisited node is found in the main loop, $c$ is incremented and a DFS is started that will visit the entire component of that node.

```text
#CC(G)
    visited[0..n] new array
    for all v ∈ V do
        visited[v] := FALSE
    c := 0
    for all v ∈ V do
        if visited[v] = FALSE then
                c := c + 1 // new connected component
            DFS-Visit(G, v)
    return c

DFS-Visit(G, v)
    visited[v] := TRUE
    for all (v, u) ∈ E do
        if visited[u] = FALSE then
            DFS-Visit(G, u)
```

**Computational cost:** $O(|V| + |E|)$.
