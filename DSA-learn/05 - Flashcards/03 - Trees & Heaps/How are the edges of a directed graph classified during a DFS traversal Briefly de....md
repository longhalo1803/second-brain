---
title: "How are the edges of a directed graph classified during a DFS traversal Briefly de..."
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
  - "How are the edges of a directed graph classified during a DFS traversal Briefly de..."
---

# 🎴 How are the edges of a directed graph classified during a DFS traversal Briefly de...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How are the edges of a directed graph classified during a DFS traversal? Briefly describe the 4 types. #card

?
During a DFS traversal on a directed graph, each edge $(u,v)$ is classified into one of the following 4 types:

- ****Tree edge****: edge belonging to the DFS spanning forest (leads to a node not yet visited).
- ****Back edge****: points from a node $u$ to an **_ancestor_ **$v$ in the DFS traversal spanning tree (direct or indirect ancestor, so any self-loops are included).
- ****Forward edge****: points from a node $u$ to a **_descendant_ **$v$ in the DFS tree (the forward edge not belonging to the spanning tree).
- ****Cross edge****: points to a node $v$ that is _**neither ancestor nor descendant**_ of $u$.
