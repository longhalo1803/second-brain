---
title: "How are distance values arranged inside the FIFO queue Q during BFS"
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
  - "How are distance values arranged inside the FIFO queue Q during BFS"
---

# 🎴 How are distance values arranged inside the FIFO queue Q during BFS

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: \*How are distance values arranged inside the FIFO queue $Q$ during BFS? #card

?
During BFS execution, the FIFO queue $Q$ maintains the nodes of the **frontier **sorted by non-decreasing distance.

For a generic level $d<n$, at the beginning of a generic iteration the queue is in one of these two states:

**Case (1):** All nodes in the queue have exact distance $d$:
`HEAD [ dist = d | dist = d | ... | dist = d ] TAIL`

**Case (2):** The queue contains nodes at distance $d$ followed by nodes at distance $d+1$:
`HEAD [ dist = d | ... | dist = d || dist = d+1 | ... | dist = d+1 ] TAIL`
