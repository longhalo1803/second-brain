---
title: "How do you modify the DFS algorithm to store the structure of the spanning forest..."
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
  - "How do you modify the DFS algorithm to store the structure of the spanning forest..."
---

# 🎴 How do you modify the DFS algorithm to store the structure of the spanning forest...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 How do you modify the DFS algorithm to store the structure of the spanning forest? Show the pseudocode with the predecessor array. #card

?
To store the spanning tree or forest, a predecessor array `prev[0..n]` is introduced.
Inside `prev[u]`, the parent node that discovered node $u$ during the traversal is stored.

```text
[#2563eb, 3pt]{{white}Main procedure}
DFS(G)
    visited[0..n] new array
    {{#d946ef}prev}[0..n] new array
    for all v ∈ V do
        visited[v] := FALSE
        {{#d946ef}prev}[v] := 0
    for all v ∈ V do
        if visited[v] = FALSE then
            DFS-Visit(G, v)
    return {{#d946ef}prev}[]

[#059669, 3pt]{{white}Recursive procedure}
DFS-Visit(G, v)
    visited[v] := TRUE
    for all (v, u) ∈ E do                // edges incident to v
        if visited[u] = FALSE then
            {{#d946ef}prev}[u] := v              // v is the parent of u
            DFS-Visit(G, u)
```

📌 Note:
At the end of the execution, all nodes $\color{#d946ef} \textsf v$ for which $\textcolor{#d946ef}{\textsf{prev}}\texttt{[}\textsf{v}\texttt{]} = 0$ are the **roots** of the trees that make up the spanning forest.

📌 Note 2: the parameter $\textsf u$, as well as $\textsf v$, does not represent the value contained in the node, but its unique identifier (ID or positional index) within the graph.
