---
title: "During an iteration of Dijkstra's algorithm, what happens when relaxing the outgoi..."
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
  - "During an iteration of Dijkstra's algorithm, what happens when relaxing the outgoi..."
---

# 🎴 During an iteration of Dijkstra's algorithm, what happens when relaxing the outgoi...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: During an iteration of Dijkstra's algorithm, what happens when relaxing the outgoing edges from the extracted node $u$ towards neighbors $v$ located in the three different "Worlds"? #card

?
Let $u$ be the node with minimum $\textsf{dist}[u]$ extracted from the Frontier. For each of its outgoing edges $(u, v)$:

- **If $v \in$ Settled World:**
  The condition $\textsf{dist}[u] + c(u,v) < \textsf{dist}[v]$ is **NEVER** satisfied, as the distance of nodes in the Settled World is already optimal and definitive.
- **If $v \in$ Frontier:**
  If $\textsf{dist}[u] + c(u,v) < \textsf{dist}[v]$, the distance $\textsf{dist}[v]$ is updated (reduced) and its priority in $Q$ is updated via $\textsf{Decrease_Priority}$.
- **If $v \in$ Far World:**
  The condition $\textsf{dist}[u] + c(u,v) < +\infty$ is **ALWAYS satisfied**. Node $v$ receives distance $\textsf{dist}[v] := \textsf{dist}[u] + c(u,v)$ and **moves from the Far World to the Frontier** (it is inserted into $Q$).
