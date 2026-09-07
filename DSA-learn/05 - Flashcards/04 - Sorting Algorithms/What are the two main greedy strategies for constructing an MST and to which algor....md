---
title: "What are the two main greedy strategies for constructing an MST and to which algor..."
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What are the two main greedy strategies for constructing an MST and to which algor..."
---

# 🎴 What are the two main greedy strategies for constructing an MST and to which algor...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the two main **greedy** strategies for constructing an **MST** and to which algorithms do they correspond? (describe briefly) #card

?
The two main greedy strategies for constructing an MST differ in the type of choice made at each step:

- **Edge-based choice - Kruskal's Algorithm (1956):**
- Sorts all edges in non-decreasing order of weight.
- At each step, it chooses the minimum-weight edge that **does not create cycles** with the already selected edges.
- Maintains a forest of subtrees that is gradually merged into a single tree.
- **Node-based choice - Prim's Algorithm (1957):**
- Starts from a single arbitrary source node.
- Grows a single tree incrementally: at each step, it chooses the minimum-weight edge connecting a node not yet in the tree to a node already present in the tree.
- Terminates when all nodes are connected.

📌 Note: both algorithms terminate when all $|V|$ nodes are connected (that is, after selecting exactly $|V| - 1$ edges).
