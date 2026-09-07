---
title: "Provide the pseudocode for Prim's algorithm."
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
  - "Provide the pseudocode for Prim's algorithm."
---

# 🎴 Provide the pseudocode for Prim's algorithm.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 Provide the pseudocode for Prim's algorithm. #card

?

```text
Prim(G = (V, E), c)
    for all v ∈ V do                     // Array initialization:
        cost[v] := +∈fty                     // cost: estimate of minimum cost to connect v
        prev[v] := NIL                       // prev: parent of v in the tree (MST)
        S[v] := 0                            // S: nodes already included in the tree (1=included, 0=no)
    choose a source node s ∈ V           // Selection of MST root
    cost[s] := 0
    S[s] := 1
    Q := make_priority_queue({(v, cost[v]) v ∈ V\)} // Build Min-Heap with all nodes
    while NOT is_empty_queue(Q) do       // Loop until all nodes are extracted
        u := DeQueue(Q)                      // Extract minimum-cost node not yet in S
        S[u] := 1
        for all (u,v) ∈ E do                 // Explore neighbors of u
            if S[v] = 0 AND cost[v] > c(u,v) then
                cost[v] := c(u,v)
                prev[v] := u
                Decrease_Priority(Q, v, cost[v])     // Update key in the Min-Heap
    return prev[]
```
