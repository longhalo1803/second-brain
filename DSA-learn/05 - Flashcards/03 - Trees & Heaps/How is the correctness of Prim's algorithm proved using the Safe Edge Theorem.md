---
title: "How is the correctness of Prim's algorithm proved using the Safe Edge Theorem"
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
  - "How is the correctness of Prim's algorithm proved using the Safe Edge Theorem"
---

# 🎴 How is the correctness of Prim's algorithm proved using the Safe Edge Theorem

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is the correctness of Prim's algorithm proved using the Safe Edge Theorem? #card

?
The proof of correctness for Prim's algorithm is based on the Safe Edge Theorem:

- In a generic iteration of Prim's algorithm, let $S$ be the set of vertices already included in the partial tree and $V \setminus S$ the set of remaining vertices.
- The pair $(S, V \setminus S)$ defines a valid **cut** of the graph.
- At each step, Prim's algorithm chooses, among all edges connecting a node in $S$ to a node in $V \setminus S$, the edge $(u,v)$ with **minimum weight**.
- By definition, the chosen edge is an **edge of minimum cost crossing the cut $(S, V \setminus S)$**.
- By the **Safe Edge Theorem**, edge $(u,v)$ is safe and belongs to an MST.Repeating this process for $|V|-1$ steps, the algorithm adds a safe edge at each iteration, ultimately producing a complete MST. $\blacksquare$
