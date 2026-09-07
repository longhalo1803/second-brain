---
title: "How do you interpret the values of the array prev[] to identify roots and paths in..."
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
  - "How do you interpret the values of the array prev[] to identify roots and paths in..."
---

# 🎴 How do you interpret the values of the array prev[] to identify roots and paths in...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How do you interpret the values of the array `prev[]` to identify roots and paths in the spanning tree? Provide an example. #card

?
The array `prev[]` represents the parent-child relationship in the spanning forest:

- If `prev[v] = 0`, then $v$ is the **root** of a tree in the forest (node from which a new component started).
- If `prev[v] = u`, then there is a directed edge in the spanning tree from $u$ to $v$ (i.e., $u$ is the parent of $v$).📝 Example:
  Given an undirected graph with 16 nodes and two connected components:

---

      v
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
      13
      14
      15
      16


      prev[v]
      0
      8
      5
      3
      1
      3
      4
      7
      7
      9
      10
      11
      14
      15
      0
      15

Interpretation:

- Nodes **1** and **15** have `prev = 0` $\implies$ they are the **roots** of the two trees in the spanning forest (the graph has 2 connected components).
- To trace back from node **12** to its root: $12 \to 11 \to 10 \to 9 \to 7 \to 4 \to 3 \to 5 \to 1$.
