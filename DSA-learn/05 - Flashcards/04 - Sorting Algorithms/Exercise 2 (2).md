---
title: "Exercise 2 (2)"
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
  - "Exercise 2 (2)"
---

# 🎴 Exercise 2 (2)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 **Exercise 2**

Consider the directed, weighted graphs shown in the figures below.
For each, determine the shortest path tree **from vertex **$1$ to all other vertices computed by the **Bellman-Ford** algorithm, assuming that the graph is stored using adjacency lists and that these are sorted in lexicographical order (**therefore, edges are relaxed by taking first all edges outgoing from node **$1$**, then all edges outgoing from node **$2$**, then from node **$3$**, and so on up to node **$6$).

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
  font-size: 20px;
  font-weight: bold;
  margin-top: 14px;
  text-align: center;
  }

  (a)

  (b)

  (c)

  (d)

  (a.1)

  (b.1)

  (c.1) #card
  ?
  📌 Remember:
  The Bellman-Ford algorithm does not select nodes based on the minimum distance (as Dijkstra would), but simply iterates through the list of edges $(u, v) \in E$ (it does not iterate over nodes!) in the order they are stored in the graph's data structure (and not all nodes necessarily have outgoing edges; in those cases, the algorithm moves on to the edges of the next node).
  🧠 Faster:
  If no relaxation occurred during an iteration (a full pass over all edges), the Bellman-Ford algorithm can terminate immediately. In fact, if no `dist` value changes during an entire pass, the input for the next iteration will be identical to the previous one, rendering subsequent passes useless.

  (a)

  (b)

  (c)

  (d)

  (a.1)

  (b.1)

  (c.1)
