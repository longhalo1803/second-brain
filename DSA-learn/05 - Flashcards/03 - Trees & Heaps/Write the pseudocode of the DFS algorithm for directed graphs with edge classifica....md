---
title: "Write the pseudocode of the DFS algorithm for directed graphs with edge classifica..."
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
  - "Write the pseudocode of the DFS algorithm for directed graphs with edge classifica..."
---

# 🎴 Write the pseudocode of the DFS algorithm for directed graphs with edge classifica...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 Write the pseudocode of the `DFS` algorithm for directed graphs with edge classification and indicate its computational complexity. #card

?

```text
DFS(G)
    pre[1..n] := new array
    post[1..n] := new array
    for all v ∈ V do
        pre[v] := 0
        post[v] := 0
    time := 0
    for all u ∈ V do
        if pre[u] = 0 then
            DFS-Visit(G, u)

DFS-Visit(G, u)
    time := time + 1
    pre[u] := time                       // starts visit of u
    for all (u, v) ∈ E do                // outgoing edges from u
        if pre[v] = 0 then
            [#28A745]{edge (u,v) is TREE}
            DFS-Visit(G, v)
        else
            if post[v] = 0 then
                [#FF4D4D]{edge (u,v) is BACK}
            else if pre[v] > pre[u] then
                [#007BFF]{edge (u,v) is FORWARD}
            else
                [#FFC107]{edge (u,v) is CROSS}
    time := time + 1
    post[u] := time                      // finishes visit of u
```

**Computational cost:** $\mathcal{O}(|V| + |E|)$, since each node and each edge are examined a constant number of times.
