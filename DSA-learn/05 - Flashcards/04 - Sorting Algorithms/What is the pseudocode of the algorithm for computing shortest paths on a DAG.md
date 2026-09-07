---
title: "What is the pseudocode of the algorithm for computing shortest paths on a DAG"
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the pseudocode of the algorithm for computing shortest paths on a DAG"
---

# 🎴 What is the pseudocode of the algorithm for computing shortest paths on a DAG

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🟢 What is the **pseudocode** of the algorithm for computing shortest paths on a DAG? #card

?

```text
Shortest_Path_DAG(G=(V,E), {#FF8C00}{c}, {#E65100}{s})
    {#00AA00}{TS := Topological_sort(G)} // {// Returns a stack}
    for all v ∈ V do
        {#00AAFF}{dist[v] := +∈fty}
    {#00AAFF}{dist[}{#E65100}{s}{#00AAFF}{] := 0}
    {#00AA00}{v := pop(TS)}
    while v ≠q {#E65100}{s} do           // {// Nodes preceding s are not reachable from s}
        {#00AA00}{v := pop(TS)}              // {// At the end of the while loop v = s (dist[s] is already 0)}
    while NOT is_empty(TS) do
        {#00AA00}{v := pop(TS)}              // {// Starts from the node following s in topological order}
        {#00AAFF}{dist[v] := _{(u,v) ∈ E} {dist[u] + } {#FF8C00}{c(u,v)}{#00AAFF}{}} // {// Relaxation over incoming edges to v}
    return {#00AAFF}{dist[]}
```

⚠️ Warning: nodes preceding $s$ in the topological sort **are not reachable** from $s$ (their distance value remains $+\infty$).
