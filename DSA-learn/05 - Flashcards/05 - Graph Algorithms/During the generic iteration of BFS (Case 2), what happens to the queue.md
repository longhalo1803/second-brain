---
title: "During the generic iteration of BFS (Case 2), what happens to the queue"
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
  - "During the generic iteration of BFS (Case 2), what happens to the queue"
---

# 🎴 During the generic iteration of BFS (Case 2), what happens to the queue

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: During the generic iteration of BFS (Case 2), what happens to the queue? #card

?
In Case (2) of breadth-first search (BFS), the queue $Q$ (i.e., the frontier) is in a mixed state: it does not consist solely of elements at the same distance, but contains simultaneously:
• Nodes at distance $d$ at the front (HEAD).
• Nodes at distance $d+1$ already inserted at the rear (TAIL).

At the beginning of the iteration, the current node $u$ (which has $dist[u] = d$) is dequeued from the head of the queue to analyze its incident edges. At this point, two scenarios can occur:

**Case (2.1) - Intermediate extraction**:
Other nodes with distance $d$ remain at the head of the queue. The structure of the queue does not change its nature: it continues to contain both elements at distance $d$ and elements at distance $d+1$.
**Case (2.2) - Level** $d$ **exhaustion**:
The newly dequeued node was the last remaining node at distance $d$. Once removed, only nodes at distance $d+1$ remain in the queue. BFS has therefore completed the exploration of level $d$: the queue becomes homogeneous again, and the system transitions back to the condition of Case 1, but for the next level ($d+1$).
