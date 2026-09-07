---
title: "Exercise 10"
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
  - "Exercise 10"
---

# 🎴 Exercise 10

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Exercise 10

Design an algorithm for the following problem:
**INPUT:** an UNDIRECTED and connected graph $G = (V, E)$
**OUTPUT:** Return TRUE if there exists an edge $e \in E$ that can be removed from graph $G$ such that the graph $G' = (V, E \setminus \{e\})$ remains connected, FALSE otherwise.
Compute the computational cost of the algorithm. #card
?

---

For both versions, the computational cost is that of a standard DFS traversal: $O(|V| + |E|)$.

**Basic idea:**
An edge $e$ can be removed without disconnecting the graph if and only if it belongs to a cycle (i.e., it is a back edge / non-tree edge in a DFS).

**VERSION 1:**
Run a DFS traversal starting from an arbitrary node, modifying the $\texttt{for}$ loop of $\textsf{DFS-Visit}$ so that the first time exploring an edge leads to an already visited node ($\textsf{visited[v] = TRUE}$), it returns TRUE (the edge belongs to a cycle and can be removed without disconnecting the graph). If the traversal finishes without finding such an edge, then return FALSE.

**VERSION 2:**
Run a DFS starting from one of the two endpoints of edge $e$ and stop when: either the other endpoint of the edge is reached (without traversing $e$ directly) and return TRUE, or the traversal finishes without discovering the other endpoint and return FALSE.
