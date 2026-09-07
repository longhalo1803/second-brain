---
title: "What is the formal definition of a cycle and a simple cycle"
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
  - "What is the formal definition of a cycle and a simple cycle"
---

# 🎴 What is the formal definition of a cycle and a simple cycle

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the formal definition of a cycle and a simple cycle? #card

?
Given a graph $G=(V,E)$:

- **Cycle:** is a sequence of nodes $\langle v_0, v_1, \dots, v_k \rangle$ that forms a path where the first and last nodes coincide ($v_0 = v_k$).
- **Simple cycle:** is a cycle whose sequence up to $v_{k-1}$ is a _simple path_ (all intermediate nodes $v_0, v_1, \dots, v_{k-1}$ are distinct from each other) and the final node closes the sequence ($v_0 = v_k$).📝 Examples:
  _Undirected graph_:
  (Simple) cycle ``

_Directed graph_:
Cycle ``

**Simple** cycle ``
