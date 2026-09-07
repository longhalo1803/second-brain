---
title: "What is the complete comparison between an Adjacency Matrix and Adjacency Lists"
tags:
  - dsa
  - flashcards
  - clrs
  - graphs
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the complete comparison between an Adjacency Matrix and Adjacency Lists"
---

# 🎴 What is the complete comparison between an Adjacency Matrix and Adjacency Lists

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the complete comparison between an Adjacency Matrix and Adjacency Lists? #card

?
Comparison between the two data structures for graphs with $n$ nodes and $m$ edges:

Operation / PropertyAdjacency MatrixAdjacency Lists**Space usage**$\Theta(n^2)$$\Theta(n + m)$**Check edge presence $(u,v)$**$\Theta(1)$$O(\text{deg}(u))$**List neighbors of node $v$**$\Theta(n)$$\Theta(\text{deg}(v))$**Optimal use case**Dense graphs ($m \in \Omega(n^2)$)Sparse graphs ($m \in O(n)$)
