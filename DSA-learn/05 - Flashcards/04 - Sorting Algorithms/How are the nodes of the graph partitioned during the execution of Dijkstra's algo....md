---
title: "How are the nodes of the graph partitioned during the execution of Dijkstra's algo..."
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
  - "How are the nodes of the graph partitioned during the execution of Dijkstra's algo..."
---

# 🎴 How are the nodes of the graph partitioned during the execution of Dijkstra's algo...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How are the nodes of the graph partitioned during the execution of Dijkstra's algorithm? (The 3 "Worlds") #card

?
During the execution of Dijkstra's algorithm, the set of nodes $V$ is divided into 3 disjoint sets:

Property of $\textsf{dist}[u]$Description**1. Settled World**
(visited nodes)$\textsf{dist}[u] \neq +\infty$Nodes extracted from the queue $Q$. Their distance from the source is **definitive** and will not change again.**2. Frontier**
(discovered, unvisited)$\textsf{dist}[u] \neq +\infty$Nodes contained in the queue $Q$. Their distance is tentative and **might still decrease**.**3. Far World**
(undiscovered)$\textsf{dist}[u] = +\infty$Nodes not yet reached by any path originating from the source.
