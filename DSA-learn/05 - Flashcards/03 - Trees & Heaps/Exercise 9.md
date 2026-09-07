---
title: "Exercise 9"
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
  - "Exercise 9"
---

# 🎴 Exercise 9

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Exercise 9

Rewrite an algorithm for the following problem:
**INPUT:** directed graph $G = (V, E)$ and two nodes $u, v \in V$.
**OUTPUT:** TRUE if there is a directed path from $u$ to $v$ and a directed path from $v$ to $u$ in $G$, FALSE otherwise.
Compute the computational cost of the algorithm. #card
?
We can build upon the work from the previous exercise by calling the path search twice. The computational cost depends on the cost of the two DFS traversals, so it is the same cost as a standard DFS traversal: $O(|V| + |E|)$.

**VERSION 1:**

```text
BidirectionalPath(G, u, v)
    return Path(G, u, v) AND Path(G, v, u)
```

**VERSION 2:**

```text
BidirectionalPath(G, u, v)
    for all w ∈ V do
        visited[w] := FALSE
    if DFS-Visit(G, u, v) = FALSE then return FALSE
    for all w ∈ V do
        visited[w] := FALSE
    return DFS-Visit(G, v, u)
```

Notice that, if no path exists in one direction, it is pointless to search in the other direction, since the output will be FALSE anyway.
