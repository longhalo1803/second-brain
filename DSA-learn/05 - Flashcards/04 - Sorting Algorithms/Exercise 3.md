---
title: "Exercise 3"
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
  - "Exercise 3"
---

# 🎴 Exercise 3

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Exercise 3

Show an example where, on the same graph, Prim's algorithm determines a different Minimum Spanning Tree from the one determined by Kruskal's algorithm.
For simplicity, it can be assumed that, in case of edges with the same weight, one can be chosen at random, meaning it is not necessary to sort edges lexicographically.
(Note: the graph must have more than one Minimum Spanning Tree). #card
?
To ensure that Prim's algorithm and Kruskal's algorithm produce two different MSTs on the same graph, the graph must admit more than one MST. This typically happens when there are cycles with edges having the same weight.

The simplest way is to take a graph where all edges have the same weight. Compute the MST using Prim's and then select another spanning tree, changing at least one edge.

Let us consider a simple undirected and connected graph consisting of 3 nodes (1, 2, 3) and 3 edges forming a triangle, all with weight 1:

Both algorithms return a valid Minimum Spanning Tree of weight 2, but the two trees consist of different edge sets: Prim produces the edge set {(1, 2), (1, 3)}, while Kruskal produces the edge set {(1, 2), (2, 3)}.
