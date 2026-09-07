---
title: "What is a path in a graph and how is its length calculated"
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
  - "What is a path in a graph and how is its length calculated"
---

# 🎴 What is a path in a graph and how is its length calculated

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is a path in a graph and how is its length calculated? #card

?
A **path** in a graph $G=(V,E)$ is a sequence of nodes $\langle v_0, v_1, v_2, \dots, v_k \rangle$ such that:

```text
(v_i, v_{i+1}) ∈ E for i = 0, 1, , k-1
```

The **length of the path** is the total number of edges that compose it, which is $k$.

📝 Example:
_Undirected graph_: the sequence of nodes $\langle 1, 2, 3, 4 \rangle$ traversed by 3 edges has length 3.

_Directed graph_: the sequence of nodes $\langle 1, 2, 3, 4, 2 \rangle$ traversed by 4 edges has length 4.
