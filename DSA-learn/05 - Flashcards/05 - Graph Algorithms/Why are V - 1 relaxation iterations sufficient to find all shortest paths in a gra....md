---
title: "Why are V - 1 relaxation iterations sufficient to find all shortest paths in a gra..."
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
  - "Why are V - 1 relaxation iterations sufficient to find all shortest paths in a gra..."
---

# 🎴 Why are V - 1 relaxation iterations sufficient to find all shortest paths in a gra...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: Why are $|V| - 1$ relaxation iterations sufficient to find all shortest paths in a graph without negative cycles? #card

?
In a graph without negative cycles, a simple shortest path from $s$ to any vertex contains at most **$|V| - 1$ edges**.

A simple path cannot visit more than $|V|$ vertices. Therefore, it can traverse at most $|V| - 1$ consecutive edges.

If a path contained $|V|$ or more edges, by the pigeonhole principle it would contain a cycle. But since all cycles have non-negative (or zero) cost, the cycle could be removed without increasing the length of the path, demonstrating that a shortest path is always simple.
