---
title: "What is the shortest paths problem on graphs in general, and what is meant by the..."
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
  - "What is the shortest paths problem on graphs in general, and what is meant by the..."
---

# 🎴 What is the shortest paths problem on graphs in general, and what is meant by the...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the shortest paths problem on graphs in general, and what is meant by the "length" of a path? #card

?
The problem consists of determining the shortest paths between nodes in a graph.

The **length** of a path is defined as:

- If the graph is unweighted: the **number of edges** it consists of.
- If the graph has weights/costs on the edges: the **sum of the weights** of the edges making up the path.📌 Note: if all weights are equal to 1, it yields the same count as the unweighted graph case.
