---
title: "[REFERENCE] How are the structural relationships between the four edge types (Tree..."
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
  - "[REFERENCE] How are the structural relationships between the four edge types (Tree..."
---

# 🎴 [REFERENCE] How are the structural relationships between the four edge types (Tree...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: [REFERENCE] How are the structural relationships between the four edge types (Tree, Back, Forward, Cross) visually displayed in a DFS traversal tree of a directed graph? #card

?
📌 Note:

- ****Tree edge****: edge belonging to the DFS spanning forest (leads to a node not yet visited).
- ****Back edge****: points from a node $u$ to an **_ancestor_ **$v$ in the DFS traversal spanning tree.
- ****Forward edge****: points from a node $u$ to a **_descendant_ **$v$ in the DFS tree (the forward edge does not belong to the spanning tree).
- ****Cross edge****: points to a node $v$ that is _**neither ancestor nor descendant**_ of $u$.
