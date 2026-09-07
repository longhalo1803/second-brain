---
title: "What is the pseudocode for Algorithm 2 for topological sorting (DFS-TS and Topolog..."
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
  - "What is the pseudocode for Algorithm 2 for topological sorting (DFS-TS and Topolog..."
---

# 🎴 What is the pseudocode for Algorithm 2 for topological sorting (DFS-TS and Topolog...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🟢 What is the pseudocode for Algorithm 2 for topological sorting (DFS-TS and TopologicalSort)? #card

?

```text
TopologicalSort(G)                   // Main procedure
    {#00C800}{visited[0..n]} new array
    S := new_stack()
    for all v ∈ V do
        {#00C800}{visited[v] := FALSE}
    for all v ∈ V do
        if {#00C800}{visited[v] = FALSE} then
            DFS-TS(G, v)
    return S

DFS-TS(G, v)
    {#00C800}{visited[v] := TRUE}
    for all (v,u) ∈ E do                 // edges outgoing from v
        if {#00C800}{visited[u] = FALSE} then
            DFS-TS(G, u)
    push(S, v)
```

📌 Note: the procedure returns the stack `S` containing the topological ordering of the nodes.
