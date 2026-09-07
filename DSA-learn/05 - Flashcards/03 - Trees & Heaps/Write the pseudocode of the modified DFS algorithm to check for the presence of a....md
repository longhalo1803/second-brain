---
title: "Write the pseudocode of the modified DFS algorithm to check for the presence of a..."
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
  - "Write the pseudocode of the modified DFS algorithm to check for the presence of a..."
---

# 🎴 Write the pseudocode of the modified DFS algorithm to check for the presence of a...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢📝 Write the pseudocode of the modified DFS algorithm to check for the presence of a cycle in an undirected graph. #card

?
The algorithm returns `TRUE` if the graph contains a cycle, `FALSE` otherwise.

```text
[#2563eb, 3pt]{{white}Main procedure}
DFS(G)
    {{#10b981}visited}[0..n] new array
    {{purple}prev}[0..n] new array
    for all v ∈ V
        {{#10b981}visited}[v] := FALSE
        {{purple}prev}[v] := 0
    for all v ∈ V // Loop to also cover disconnected graphs
        if {{#10b981}visited}[v] = FALSE AND DFS-Visit(G, v) // Start visit if not visited
            then return TRUE // Cycle found
    return FALSE // No cycle in the graph

[#059669, 3pt]{{white}Recursive procedure}
DFS-Visit(G, v)
    {{#10b981}visited}[v] := TRUE // Mark v as visited
    for all (v, u) ∈ E // Examine edges incident to v
        if {{#10b981}visited}[u] = FALSE // If neighbor u is not yet visited...
            then {{purple}prev}[u] := v // ...set v as parent of u
        // If u is not the parent and is already visited (cycle) or recursion finds a cycle
        if {{purple}prev}[v] ≠q u AND ({{#10b981}visited}[u] = TRUE OR DFS-Visit(G, u))
            then return TRUE // Cycle found
    return FALSE // No cycle found
```

(`DFS-Visit` is called from the main loop exactly $k$ times, where $k$ is the number of connected components, which also corresponds to the number of trees if the components contain no cycles. The loop `for all v in V` guarantees full coverage, preventing the algorithm from stopping after the first component: without it, exploration would halt at the first component encountered and the rest of the graph would remain unexplored)

Version without short-circuit requirement:

```text
[#2563eb, 3pt]{{white}Main procedure}
DFS-HasCycle(G)
    {{#10b981}visited}[0..n], {{purple}prev}[0..n] new array
    for all v ∈ V do
        {{#10b981}visited}[v] := FALSE, {{purple}prev}[v] := 0
    for all v ∈ V do
        if {{#10b981}visited}[v] = FALSE AND DFS-Visit-Cycle(G, v) then
            return TRUE                          // cycle found
    return FALSE                         // no cycle

[#059669, 3pt]{{white}Recursive procedure}
DFS-Visit-Cycle(G, v)
    {{#10b981}visited}[v] := TRUE
    for all (v, u) ∈ E do
        if {{#10b981}visited}[u] = FALSE then
            {{purple}prev}[u] := v
            if DFS-Visit-Cycle(G, u) then
                return TRUE
        else if {{purple}prev}[v] ≠q u then  // u visited and u is not the parent of v
            return TRUE                          // found back-edge!
    return FALSE
```

📌 Remember:
An edge $(v, u)$ is a **back-edge** (and therefore indicates a cycle) if and only if:

```text
visited[u] = TRUE AND prev[v] ≠q u
```

that is, $u$ is already visited and **is not the immediate parent** of $v$.
