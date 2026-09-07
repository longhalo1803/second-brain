---
title: "Which type of edge definitely indicates the presence of a cycle in a directed grap..."
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
  - "Which type of edge definitely indicates the presence of a cycle in a directed grap..."
---

# 🎴 Which type of edge definitely indicates the presence of a cycle in a directed grap...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Which type of edge definitely indicates the presence of a cycle in a directed graph during a DFS? Why do Forward and Cross edges not form cycles? #card

?
In a directed graph, the presence of at least one **Back edge** indicates that there is a **cycle** in the graph.

**Why do the other edges not form cycles?**
_Forward_ and _Cross_ edges cannot form cycles because their direction is "wrong" (it goes from an ancestor to a descendant or between disjoint branches of the forest), preventing traversal back up the path to return to the starting node.

⚠️ Warning:
Unlike undirected graphs, in directed graphs edges that are not part of the spanning tree **do not always indicate the presence of a cycle**: only _back edges_ do!

📌 Note:

- ****Tree edge****: edge belonging to the DFS spanning forest (leads to a node not yet visited).
- ****Back edge****: points from a node $u$ to an **_ancestor_ **$v$ in the DFS traversal spanning tree.
- ****Forward edge****: points from a node $u$ to a **_descendant_ **$v$ in the DFS tree (the forward edge does not belong to the spanning tree).
- ****Cross edge****: points to a node $v$ that is _**neither ancestor nor descendant**_ of $u$.
