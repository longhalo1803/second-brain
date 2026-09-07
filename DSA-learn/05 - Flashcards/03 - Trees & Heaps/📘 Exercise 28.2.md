---
title: "📘 Exercise 28.2"
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
  - "📘 Exercise 28.2"
---

# 🎴 📘 Exercise 28.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 28.2

**Input:** A directed graph $G = (V, E)$ and a vertex coloring function $col : V \to \{R, Vd\}$ (Red and Green).
**Output:** TRUE if $G$ contains a simple cycle composed exclusively of green ($Vd$) nodes, FALSE otherwise.

- Show two examples with at least 5 nodes (one TRUE, one FALSE).
- Describe an efficient algorithm and provide pseudocode.
- Analyze computational complexity.
- What should be modified if we look for an alternating simple cycle (green, red, green, red...)? #card
  ?
  **Reasoning:**
  Filter the graph to the subgraph induced by green vertices $V_{green}$. Finding a cycle in a directed graph is accomplished by detecting back-edges during DFS (nodes in state GRAY).

**Pseudocode:**

```text
Algorithm HasGreenCycle(G, col):
    state[] ≤ftarrow array of size |V| initialized to WHITE
    for each u ∈ V do
        if col(u) = Vd state[u] = WHITE then
            if DFS_GreenCycle(u, G, col, state) then return TRUE
    return FALSE

Function DFS_GreenCycle(u, G, col, state):
    state[u] ≤ftarrow GRAY
    for each v ∈ Adj[u] do
        if col(v) = Vd then
            if state[v] = GRAY then return TRUE
            if state[v] = WHITE then
                if DFS_GreenCycle(v, G, col, state) then return TRUE
    state[u] ≤ftarrow BLACK
    return FALSE
```

**Complexity:**
Standard DFS traversal takes $O(|V| + |E|)$ time and $O(|V|)$ space.

**Alternating Cycle Extension:**
Construct an auxiliary bipartite graph where state is $(u, color)$, or simply during DFS only follow edge $(u, v)$ if $col(u) \ne col(v)$. Detect a back-edge to an ancestor with the proper alternating parity.
