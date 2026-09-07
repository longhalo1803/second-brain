---
title: "If a graph contains a directed cycle, is it possible to find a topological orderin..."
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
  - "If a graph contains a directed cycle, is it possible to find a topological orderin..."
---

# 🎴 If a graph contains a directed cycle, is it possible to find a topological orderin...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: If a graph contains a directed cycle, is it possible to find a topological ordering? Why? #card

?
**No**, if a graph contains a directed cycle, it is **not possible** to find a topological ordering.

**Why?**
In the presence of a cycle (e.g., $u \to v \to \dots \to u$), there is no arrangement of vertices in which all edges go from left to right. Whatever ordering is chosen, there will always be _at least one edge going "backwards"_ (from right to left).

⚠️ Warning: the existence of a topological ordering is a **necessary and sufficient** condition to state that the graph is a DAG.
