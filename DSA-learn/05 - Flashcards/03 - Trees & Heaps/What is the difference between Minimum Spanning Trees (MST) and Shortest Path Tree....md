---
title: "What is the difference between Minimum Spanning Trees (MST) and Shortest Path Tree..."
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
  - "What is the difference between Minimum Spanning Trees (MST) and Shortest Path Tree..."
---

# 🎴 What is the difference between Minimum Spanning Trees (MST) and Shortest Path Tree...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the difference between Minimum Spanning Trees (MST) and Shortest Path Trees (SPT for the SSSP problem)? #card

?
The difference lies in their different optimization objectives:

---

      Property
      Minimum Spanning Tree (MST)
      Shortest Path Tree (SPT)




      Objective
      Minimize the **total sum of weights** of all edges connecting the entire graph.
      Minimize the **distance (sum of weights along the path)** between a source node $s$ and each other node $v$.


      Source dependence
      Does not depend on a source or destination vertex (global for the entire graph).
      Depends specifically on the choice of source $s$.


      Common algorithms
      Kruskal, Prim.
      Dijkstra, Bellman-Ford.


      Typical use cases
      Local area network (LAN) design, water piping, or electrical grids.
      GPS navigation, IP routing protocols, and driving directions.

▷ **Shortest Path** asks: What is the minimum cost required to travel from a specific vertex to another?▷ **Minimum Spanning Tree** asks: What is the minimum total cost required to connect all vertices together?
One deals with the journey between two points, the other deals with building an entire network/subgraph.

📝 Example 1:

📝 Example 2:

- The **MST** uses the edges of weights 1, 2, 2 for a total cost equal to $1 + 2 + 2 = 5$.
- The **Shortest Path Tree from source 1** will prefer the dashed direct edge from 1 to 4 with weight 4 instead of the longer path of weight $1+2+2=5$, yielding a different structure.
