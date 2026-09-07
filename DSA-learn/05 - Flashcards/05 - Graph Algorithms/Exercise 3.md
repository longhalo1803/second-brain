---
title: "Exercise 3"
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
  - "Exercise 3"
---

# 🎴 Exercise 3

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 Exercise 3

Given a graph $G = (V, E)$ and a node $v \in V$, write a function for each of the following cases:

1. $G$ is undirected; the function $\textsf{neighbors}(v)$ returns the list of nodes incident to $v$.
2. $G$ is directed; the function $\textsf{out-neighbors}(v)$ returns the list of nodes reachable from $v$ with an edge outgoing from $v$ (i.e., for which $(v, u) \in E$ exists).
3. $G$ is directed; the function $\textsf{in-neighbors}(v)$ returns the list of nodes $u$ that have an outgoing edge incident to $v$ (i.e., for which $(u, v) \in E$ exists).

Write two versions, one assuming the graph is represented using an adjacency matrix, and one using adjacency lists, and for each version, calculate the computational cost of the function. #card
?
