---
title: "What is the pseudocode of the Bellman-Ford algorithm (basic version)"
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
  - "What is the pseudocode of the Bellman-Ford algorithm (basic version)"
---

# 🎴 What is the pseudocode of the Bellman-Ford algorithm (basic version)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 🟢 What is the pseudocode of the Bellman-Ford algorithm (basic version)? #card

?

```text
Bellman-Ford(G, c, s)
    ≤ft. for all u ∈ V
        {#1E88E5}{ dist[u] := +∈fty}
        {#9B59B6}{ prev[u] := NIL}
    {#1E88E5}{ dist[s] := 0} } {currentColor}{[0.5ex]{4.5cm}{0.3pt}} // Initialize(G,s)
    for i := 1 to |V| - 1 do
        for all (u, v) ∈ E do                // |V|-1 relaxation iterations
            ≤ft. if {#1E88E5}{dist[v]} > {#1E88E5}{dist[u]} + {#C58A00}{c(u, v)} then
                {#1E88E5}{dist[v] := dist[u]} + {#C58A00}{c(u, v)}
                {#9B59B6}{prev[v] := u} } [0.5ex]{0cm}{0.3pt} // Relax(u,v)
    return {#9B59B6}{prev[]}
```

⚠️ Warning:
As seen from the pseudocode, the Bellman-Ford algorithm does not select nodes based on minimum distance (as Dijkstra would), but simply iterates through the list of edges $(u, v) \in E$ (it does not iterate over the nodes!) in the order they are stored in the graph data structure.

Step by step (optimized version):
