---
title: "What is the fundamental idea behind the Bellman-Ford algorithm and how many relaxa..."
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
  - "What is the fundamental idea behind the Bellman-Ford algorithm and how many relaxa..."
---

# 🎴 What is the fundamental idea behind the Bellman-Ford algorithm and how many relaxa...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the fundamental idea behind the Bellman-Ford algorithm and how many relaxation iterations does it require? #card

?
The fundamental idea of the Bellman-Ford algorithm is to **repeatedly relax ALL edges of the graph** a sufficient number of times.

**For how many iterations?**
Relaxing all edges **$|V| - 1$ times** is sufficient to guarantee that all shortest paths are computed.

📌 Note:
Unlike Dijkstra, Bellman-Ford does not pick nodes greedily, but cyclically updates the entire set of edges $E$.
