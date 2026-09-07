---
title: "Exercise 4"
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
  - "Exercise 4"
---

# 🎴 Exercise 4

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Exercise 4

Show an example of a graph $G$ such that, choosing two nodes $u$ and $v$ in the graph, DFS traversals started from $u$ and from $v$ produce different spanning trees. Show the resulting spanning trees in the following two cases:

1. the graph $G$ is directed and the two spanning trees share at least one node;
2. the graph $G$ is undirected and connected.
   📌 Note: assume that the DFS traversal analyzes edges incident to (outgoing from) a node in lexicographical order. #card
   ?
   **1. Directed graph:**
   Consider the directed graph $G = (V, E)$ with nodes $V = \{1, 2, 3\}$ and edges $E = \{(1, 2), (2, 3)\}$.
   • If the traversal starts at $u = 1$: it discovers $2$ via $(1, 2)$ and then $3$ via $(2, 3)$. The spanning tree contains the edges $\{(1, 2), (2, 3)\}$ and spans nodes $\{1, 2, 3\}$.
   • If the traversal starts at $v = 2$: it discovers $3$ via $(2, 3)$. Then the outer DFS loop restarts from $1$ (not yet visited). The resulting tree/forest has only $\{(2, 3)\}$ as tree edges.
   The two spanning trees are different and share the nodes $\{2, 3\}$.

**2. Undirected and connected graph:**
Consider an undirected 3-node cycle $V = \{1, 2, 3\}$ with edges $\{(1, 2), (2, 3), (1, 3)\}$. Examining edges in lexicographical order:
• If the traversal starts at $u = 1$: from $1$ it visits $2$ via $(1, 2)$, from $2$ it visits $3$ via $(2, 3)$. The edge $(1, 3)$ finds $3$ already visited (back edge). The spanning tree contains the edges $\{(1, 2), (2, 3)\}$.
• If the traversal starts at $v = 3$: from $3$ it visits $1$ via $(3, 1)$ (since $1 < 2$), from $1$ it visits $2$ via $(1, 2)$. The spanning tree contains the edges $\{(3, 1), (1, 2)\}$.
The two spanning trees are clearly different.
