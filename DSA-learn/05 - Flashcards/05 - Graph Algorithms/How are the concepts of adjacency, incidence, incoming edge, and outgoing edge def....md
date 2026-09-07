---
title: "How are the concepts of adjacency, incidence, incoming edge, and outgoing edge def..."
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
  - "How are the concepts of adjacency, incidence, incoming edge, and outgoing edge def..."
---

# 🎴 How are the concepts of adjacency, incidence, incoming edge, and outgoing edge def...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How are the concepts of adjacency, incidence, incoming edge, and outgoing edge defined in a graph? #card

?
Given a graph $G=(V,E)$:

- a node $v$ is _adjacent_ to a node $u$ if the edge $(u,v) \in E$ (or $(v,u) \in E$) exists.
- an edge $(u,v)$ is said to be _incident_ to nodes $u$ and $v$.

For **directed** graphs, given a directed edge $(v,u) \in E$:

- It is an edge directed from node $v$ to node $u$;
- It is an **outgoing** edge from node $v$;
- It is an **incoming** edge to node $u$.
