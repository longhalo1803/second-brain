---
title: "What is the state of the three sets at the beginning of the first iteration and up..."
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
  - "What is the state of the three sets at the beginning of the first iteration and up..."
---

# 🎴 What is the state of the three sets at the beginning of the first iteration and up...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the state of the three sets at the beginning of the first iteration and upon termination of BFS? What is the value of $d$ at the end? #card

?
**Initial and Final State of BFS:**

- **Initialization ($d = 0$):**
- **Settled World:** Empty.
- **Frontier:** Contains only the source $s$ with $\text{dist}[s] = 0$.
- **Far World:** Contains all other nodes $V \setminus \{s\}$ with $\text{dist} = +\infty$.

- **Termination (FIFO Queue empty):**
- **Frontier:** Empty (no remaining discovered nodes left to explore).
- **Settled World:** Contains **all nodes reachable** from $s$, each with its true minimum distance.
- **Far World:** Contains only nodes **NOT reachable** from $s$ (which keep $\text{dist} = +\infty$).
  📌 **Final value of $d$:
  **At the end of the algorithm, $d$ is equal to the **maximum distance** (eccentricity of $s$) between the source $s$ and any node reachable from it in the graph.

---
