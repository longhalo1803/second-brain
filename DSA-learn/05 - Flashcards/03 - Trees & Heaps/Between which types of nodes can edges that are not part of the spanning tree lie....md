---
title: "Between which types of nodes can edges that are not part of the spanning tree lie..."
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
  - "Between which types of nodes can edges that are not part of the spanning tree lie..."
---

# 🎴 Between which types of nodes can edges that are not part of the spanning tree lie...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Between which types of nodes can edges that are **not part** of the spanning tree lie in an **undirected** graph? #card

?
In an **undirected** graph, edges $(u,v)$ that do not belong to the BFS spanning tree can only connect:

- **Tree nodes at the same level**: nodes for which $\text{dist}[u] = \text{dist}[v]$ (e.g., edge $(7, 8)$ where both have distance 2).
- **Tree **nodes on two consecutive levels: nodes for which $\text{dist}[v] = \text{dist}[u] + 1$ but where the edge was not used to discover $v$ (e.g., edge $(9, 5)$).📝 Example:

      dist



            1
            2
            3
            4
            5
            6
            7
            8
            9
            10
            11
            12


            4
            3
            0
            1
            1
            2
            2
            2
            2
            3
            4
            4






      prev



            1
            2
            3
            4
            5
            6
            7
            8
            9
            10
            11
            12


            2
            6
            0
            3
            3
            5
            4
            4
            4
            9
            10
            2

📌 Remember:
The `dist` array indicates distances from the source node (in this example, 3).
The `prev` array is the vector of parents (predecessors) of the BFS tree generated from the root (in this example, 3) and indicates, for each node $v$ (top row $1, 2, \dots, 12$), the parent node (bottom row) from which $v$ was visited and explored during the BFS.
⚠️ Warning:
In an undirected graph, **there CANNOT be BFS edges that skip two or more levels** (e.g., between level 1 and level 3), because if such an edge existed, the level 3 node would have been discovered at distance 2!
