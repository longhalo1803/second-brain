---
title: "What is the pseudocode of the Bellman-Ford algorithm with the early termination va..."
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
  - "What is the pseudocode of the Bellman-Ford algorithm with the early termination va..."
---

# 🎴 What is the pseudocode of the Bellman-Ford algorithm with the early termination va...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 🟢📝 What is the pseudocode of the Bellman-Ford algorithm with the "early termination" variant?

📌 Hint:
The early termination optimization allows **stopping the algorithm before completing all $|V| - 1$ iterations** if the distances have already all converged to their minimum values.

A boolean flag is introduced, for instance $\textsf{continueLoop}$:

- At the beginning of the iteration, set $\textsf{continueLoop} := \textsf{False}$.
- If the distance of at least one node is updated during the edge scan, set $\textsf{continueLoop} := \textsf{True}$.
- If at the end of the iteration $\textsf{continueLoop} == \textsf{False}$, it means that no relaxation produced changes: the shortest paths have already been found and the loop terminates immediately.Start from here:

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
                {#9B59B6}{prev[v] := u} } {currentColor}{[0.5ex]{0cm}{0.3pt}} // Relax(u,v)
    for all (u, v) ∈ E do
        if {#1E88E5}{dist[v]} > {#1E88E5}{dist[u]} + {#C58A00}{c(u, v)} then // Negative cycle check
            return "negative cycle exists"
    return {#9B59B6}{prev[]}
``` #card
?
```text
Bellman-Ford-EarlyTermination(G, c, s)
    ≤ft. for all u ∈ V do
        {#1E88E5}{dist[u]} := +∈fty
        {#9B59B6}{prev[u]} := NIL
    {#1E88E5}{dist[s]} := 0 } {currentColor}{[0.5ex]{4.4cm}{0.3pt}} // Initialize(G,s)
        {#2E7D32}{ continueLoop := True; i := 1}
    {#2E7D32}{ while i  {#1E88E5}{dist[u]} + {#C58A00}{c(u, v)} then
                {#1E88E5}{dist[v]} := {#1E88E5}{dist[u]} + {#C58A00}{c(u, v)}
                {#9B59B6}{prev[v]} := u } [0.5ex]{0cm}{0.3pt} // Relax(u,v)
                {#2E7D32}{ continueLoop := True}
        {#2E7D32}{ i := i + 1}
    {#E53935}{ if continueLoop then}     // Negative cycle check if not terminated earlier
        for all (u, v) ∈ E do
            if {#1E88E5}{dist[v]} > {#1E88E5}{dist[u]} + {#C58A00}{c(u, v)} then
                return "negative cycle exists"
    return {#9B59B6}{prev[]}
````
