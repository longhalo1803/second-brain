---
title: "How are the three Worlds configured at the beginning of Dijkstra's algorithm and w..."
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
  - "How are the three Worlds configured at the beginning of Dijkstra's algorithm and w..."
---

# 🎴 How are the three Worlds configured at the beginning of Dijkstra's algorithm and w...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How are the three "Worlds" configured at the beginning of Dijkstra's algorithm and what is the termination condition? #card

?
**Initialization (initial state):**

- **Settled World:** Empty ($\emptyset$);
- **Frontier:** Contains only the source node $s$, with $\textsf{dist}[s] = 0$;
- **Far World:** Contains all other nodes of the graph $V \setminus \{s\}$, with $\textsf{dist}[v] = +\infty$.

**Termination condition:**
The algorithm terminates when the **Frontier becomes empty** (i.e., when the priority queue $Q$ is completely emptied).

At the end of the algorithm, all nodes reachable from $s$ will be in the Settled World with their shortest distances computed correctly; unreachable nodes do not remain in the Far World, because the queue $Q$ continues to extract nodes until it is completely emptied (eventually extracting those with distance $+\infty$ as well).
