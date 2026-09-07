---
title: "What types of non-tree edges can appear during a BFS traversal on a directed graph"
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
  - "What types of non-tree edges can appear during a BFS traversal on a directed graph"
---

# 🎴 What types of non-tree edges can appear during a BFS traversal on a directed graph

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What types of **non-tree** edges can appear during a BFS traversal on a **directed** graph? #card

?
In a **directed** graph, unlike an undirected one, the direction of the arrows allows 4 types of **edges that do **not** belong to the BFS tree**:

      Edge type
      Description
      Example


      Same level
      Edge from a node to another at the same tree level.
      $\text{dist}[u] = \text{dist}[v]$


      Next level
      Edge towards a node at the immediately following level (not used for the first discovery).
      Edge $(5, 9)$


      Back edge (Ancestor)
      Directed edge from a node to one of its ancestors in the tree (goes up multiple levels).
      Edge $(7, 4)$


      From non-tree to tree
      Edge from an unreachable node (or not yet discovered in the tree) towards a tree node.
      Edge $(2, 6)$

📝 Example:

      **dist**



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


            +inf
            +inf
            0
            1
            1
            2
            3
            2
            2
            3
            4
            +inf






      **prev**



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


            0
            0
            0
            3
            3
            5
            8
            4
            4
            9
            10
            NIL

📌 Remember:
**`dist` **(distance): stores the minimum number of steps (edges) required to reach each node starting from the source. If a node is unreachable from 3, its distance remains $+\infty$.
**`prev` **(predecessor / parent): stores the node from which that particular node was visited for the first time. Used to reconstruct the entire path backwards.
