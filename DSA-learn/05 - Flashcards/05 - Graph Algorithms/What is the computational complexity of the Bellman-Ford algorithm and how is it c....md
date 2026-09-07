---
title: "What is the computational complexity of the Bellman-Ford algorithm and how is it c..."
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
  - "What is the computational complexity of the Bellman-Ford algorithm and how is it c..."
---

# 🎴 What is the computational complexity of the Bellman-Ford algorithm and how is it c...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the computational complexity of the Bellman-Ford algorithm and how is it calculated?

````text
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
``` #card
?
The computational complexity of Bellman-Ford is **$O(|V| \cdot |E|)$**.

**Cost analysis:**

- **Initialization:** scans all vertices $V$ to initialize $\textsf{dist}$ and $\textsf{prev}$ $\to O(|V|)$.
- **Outer loop:** runs $|V| - 1$ times.
- **Inner loop:** examines all $|E|$ edges at each iteration to perform the relaxation $\to O(|E|)$.
Total cost: $O(|V|) + ( |V| - 1 ) \cdot O(|E|) = O(|V| \cdot |E|)$.
````
