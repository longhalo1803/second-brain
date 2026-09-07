---
title: "What is a complete graph How many edges does a complete graph with n nodes have (d..."
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
  - "What is a complete graph How many edges does a complete graph with n nodes have (d..."
---

# 🎴 What is a complete graph How many edges does a complete graph with n nodes have (d...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is a complete graph? How many edges does a complete graph with $n$ nodes have (directed and undirected cases)? #card

?
A **complete graph** is a graph in which an edge exists between every pair of distinct nodes.
**
Complete undirected graph:**

$$
m = (n-1) + (n-2) + \dots + 1 = \frac{(n-1)n}{2} \in \Theta(n^2)
$$

**
Complete directed graph (without self-loops):**

$$
m = n \cdot (n-1) = n^2 - n \in \Theta(n^2)
$$
