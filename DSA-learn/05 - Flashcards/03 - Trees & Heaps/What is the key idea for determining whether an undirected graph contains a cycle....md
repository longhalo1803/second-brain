---
title: "What is the key idea for determining whether an undirected graph contains a cycle..."
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
  - "What is the key idea for determining whether an undirected graph contains a cycle..."
---

# 🎴 What is the key idea for determining whether an undirected graph contains a cycle...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the key idea for determining whether an undirected graph contains a cycle using DFS? #card

?
An undirected graph contains a cycle if and only if a **Back-Edge** is detected during the DFS traversal.

📌 Note: when running DFS on an undirected graph, the traversal assigns a "virtual" direction to edges as they are explored, but the graph remains undirected.

- A _back-edge_ is an edge that connects the current node $v$ to an already visited node $u$ that **is not the immediate parent** of $v$ in the spanning tree ($u \neq prev[v]$).

- Since $u$ has already been visited and is an ancestor of $v$, there already exists a unique path in the spanning tree connecting $u$ to $v$.

- The existence of the additional edge $(v, u)$ closes the path, creating a **simple cycle** formed by the path in the tree plus the edge $(v,u)$.
