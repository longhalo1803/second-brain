---
title: "Why does Dijkstra's algorithm fail if the graph contains edges with negative weigh..."
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
  - "Why does Dijkstra's algorithm fail if the graph contains edges with negative weigh..."
---

# 🎴 Why does Dijkstra's algorithm fail if the graph contains edges with negative weigh...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Why does Dijkstra's algorithm fail if the graph contains edges with negative weights (even in the absence of negative cycles)? #card

?
Dijkstra's algorithm relies on the existence of a **"settled world"**: once a node $u$ is extracted from the priority queue, it is assumed that its distance $\textsf{dist}[u]$ is final and can no longer change.

If there are edges with negative weight $c(u, v) < 0$, relaxing an edge $(u, v)$ outgoing from a node $u$ might decrease the distance of a node $v$ that already belongs to the "settled world" (i.e., was already extracted and processed earlier).

In the presence of negative weights, **there is no settled world**, because a node considered final could later find an even shorter path.
