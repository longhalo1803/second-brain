---
title: "Exercise 1"
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
  - "Exercise 1"
---

# 🎴 Exercise 1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 **Exercise 1**

Consider the directed, weighted graphs shown in the figures below.
For each of them, determine the shortest path tree from vertex $1$ to all other vertices computed by **Dijkstra's** algorithm, assuming that the graph is stored using adjacency lists and that these are sorted in lexicographical order (i.e., traversing the list from head to tail, the nodes in the list contain the identifiers of neighboring nodes in increasing order), and that, **in case of a tie in priority, the node with the smaller identifier is extracted from the queue**.

⚠️ Attention:
The solutions are unique because the problem statements provide precise instructions on the order in which to examine edges and nodes and how to break ties.
Do not make the following **mistakes**:

- Using a FIFO queue instead of a priority queue.
- Updating the parent when a path of the same length as the one already found is discovered (the update must be performed ONLY in case of a path with strictly smaller cost than the one already found).
- In case of nodes with the same maximum priority (i.e., minimum distance from the source) in the priority queue, NOT choosing the one with the smallest identifier.

  .graph-container {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
  justify-content: center;
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  font-family: system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
  color: currentColor;
  }

  .graph-card {
  flex: 1 1 320px;
  max-width: 380px;
  border: 1px solid currentColor;
  border-radius: 12px;
  padding: 16px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  align-items: center;
  background: transparent;
  }

  .graph-card svg {
  width: 100%;
  height: auto;
  max-width: 1000px;
  overflow: visible;
  }

  .graph-label {
  font-size: 18px;
  font-weight: bold;
  margin-top: 14px;
  text-align: center;
  }

  (a) - step by step

  (b)

  (c)

  (d)

  (a.1)

  (b.1)

  (c.1)

  (d.1) #card
  ?
  (a) - step by step

  (b)

  (c)

  (d)

  (a.1)

  (b.1)

  (c.1)

  (d.1)
