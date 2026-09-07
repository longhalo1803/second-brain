---
title: "How is the test for the presence of cycles in a directed graph structured (Directe..."
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
  - "How is the test for the presence of cycles in a directed graph structured (Directe..."
---

# 🎴 How is the test for the presence of cycles in a directed graph structured (Directe...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is the test for the presence of cycles in a directed graph structured (Directed Graph Cycle Test) and what is its complexity? #card

?
A DFS traversal is performed.
If during the exploration of outgoing edges from a node a **Back edge** is detected (i.e., an edge $(u,v)$ with $\textsf{post}[v] = 0$), the algorithm signals the presence of a cycle by returning `TRUE`.
If the traversal finishes without finding any back edges, it returns `FALSE`.

**Pseudocode:**

```text
HasCycle(G)
    pre[1..n] := new array
    post[1..n] := new array
    for all v ∈ V do
        pre[v] := 0
        post[v] := 0
    time := 0
    for all u ∈ V do
        if pre[u] = 0 then
            if DFS-Cycle-Visit(G, u) = TRUE then return TRUE
    return FALSE

DFS-Cycle-Visit(G, u)
    time := time + 1
    pre[u] := time
    for all (u, v) ∈ E do
        if pre[v] = 0 then
            if DFS-Cycle-Visit(G, v) = TRUE then return TRUE
        else if post[v] = 0 then
            [#FF4D4D, 1pt]{return TRUE} // Back Edge found!
    time := time + 1
    post[u] := time
    return FALSE
```

**Computational cost:** $\mathcal{O}(|V| + |E|)$.
