---
title: "Exercise 8"
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
  - "Exercise 8"
---

# 🎴 Exercise 8

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Exercise 8

Rewrite an algorithm for the following problem:
**INPUT:** graph $G = (V, E)$ (directed or undirected) and two nodes $u, v \in V$.
**OUTPUT:** TRUE if there is a path from $u$ to $v$ in $G$, FALSE otherwise.
Compute the computational cost of the algorithm. #card
?
The problem can be solved in two ways:

- use the previously seen `DFS-visit` procedure by writing a main function similar to the DFS procedure where a traversal starts only from node `u` (instead of looping over all nodes with visited equal to FALSE) and then check whether `visited[v]` is TRUE or FALSE.
- also modify `DFS-visit` so that it stops as soon as node `v` is reached. The new `DFS-visit(G,w,v)` returns True if `v` lies in the subtree rooted at `w` and False otherwise.
  In the worst case, since we cannot rule out that the graph is connected and node $v$ is the last to be reached, the computational cost is the same as a standard DFS traversal: $O(|V| + |E|)$.

**VERSION 1** (traversal from $u$ and final check of $\textsf{visited}[v]$):

```text
Path(G, u, v)
    for all w ∈ V do
        visited[w] := FALSE
    DFS-Visit(G, u)
    return visited[v]
```

**VERSION 2** (stopping as soon as $v$ is reached):

```text
Path(G, u, v)
    for all w ∈ V do
        visited[w] := FALSE
    return DFS-Visit(G, u, v)
```

```text
DFS-Visit(G, w, v)
    visited[w] := TRUE
    for all (w, x) ∈ E do
        if x = v then return TRUE
        if DFS-Visit(G, x, v) = TRUE then return TRUE
    return FALSE
```

Note that when $v$ is found, the pending recursive calls also terminate and no further edges are explored (to avoid unnecessary work). Furthermore, $\textsf{DFS-Visit}$ is never invoked on $v$, as it is not needed.
