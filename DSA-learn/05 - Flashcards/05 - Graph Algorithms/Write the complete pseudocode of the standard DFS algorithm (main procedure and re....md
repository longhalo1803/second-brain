---
title: "Write the complete pseudocode of the standard DFS algorithm (main procedure and re..."
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
  - "Write the complete pseudocode of the standard DFS algorithm (main procedure and re..."
---

# 🎴 Write the complete pseudocode of the standard DFS algorithm (main procedure and re...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 🟢 Write the complete pseudocode of the standard DFS algorithm (main procedure and recursive procedure) for a graph $G=(V,E)$. #card

?

```text
[#2563eb, 3pt]{{white}Main procedure}
DFS(G)
    visited[0..n] new array
    for all v ∈ V do
        visited[v] := FALSE
    for all v ∈ V do
        if visited[v] = FALSE then
            DFS-Visit(G, v)

[#059669, 3pt]{{white}Recursive procedure}
DFS-Visit(G, v)
    visited[v] := TRUE
    // examine node v (pre-visit case)
    for all (v, u) ∈ E do                // edges incident to v
        if visited[u] = FALSE then
            DFS-Visit(G, u)
    // examine node v (post-visit case)
```
