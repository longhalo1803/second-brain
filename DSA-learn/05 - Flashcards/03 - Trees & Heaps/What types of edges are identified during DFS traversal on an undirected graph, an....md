---
title: "What types of edges are identified during DFS traversal on an undirected graph, an..."
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
  - "What types of edges are identified during DFS traversal on an undirected graph, an..."
---

# 🎴 What types of edges are identified during DFS traversal on an undirected graph, an...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What types of edges are identified during DFS traversal on an undirected graph, and what role do they play? #card

?
During the execution of DFS on an undirected graph, the edges of the graph are divided into two distinct categories:

- **Tree Edges:** edges $(v, u)$ whose exploration leads to a node $u$ that is **not yet visited**. These edges form the spanning tree (or forest) of the graph.
- **Back Edges:** edges $(v, u)$ whose exploration leads to a node $u$ that is **already visited** (other than the immediate parent of $v$). A back edge connects a node to an ancestor in the DFS tree and indicates the presence of a **cycle** in the graph.

⚠️ Warning:
In an **undirected** graph, during DFS there are **never** any _forward edges_ or _cross edges_: every non-tree edge is a _back edge_.
Since adjacency is bidirectional, the first endpoint $u$ visited by DFS immediately explores the other endpoint $v$, necessarily making it its descendant in the tree. Therefore, $v$ can never lie in a separate branch (_cross edge_) nor be rediscovered from top to bottom (_forward edge_), making every other edge a direct link to an ancestor (_back edge_).
