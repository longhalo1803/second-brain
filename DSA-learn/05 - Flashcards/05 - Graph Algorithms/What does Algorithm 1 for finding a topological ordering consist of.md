---
title: "What does Algorithm 1 for finding a topological ordering consist of"
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
  - "What does Algorithm 1 for finding a topological ordering consist of"
---

# 🎴 What does Algorithm 1 for finding a topological ordering consist of

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What does Algorithm 1 for finding a topological ordering consist of? #card

?
Algorithm 1 determines the topological ordering by **progressively removing sources** and follows these steps:

- Find a vertex in the graph with no incoming edges (a _source_ vertex).
- Append the selected vertex to the topological ordering.
- Remove the vertex from the graph along with all its outgoing edges.
- Repeat steps 1–3 until all vertices have been removed from the graph.
