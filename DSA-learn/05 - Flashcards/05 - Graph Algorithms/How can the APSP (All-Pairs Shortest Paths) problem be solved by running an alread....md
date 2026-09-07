---
title: "How can the APSP (All-Pairs Shortest Paths) problem be solved by running an alread..."
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
  - "How can the APSP (All-Pairs Shortest Paths) problem be solved by running an alread..."
---

# 🎴 How can the APSP (All-Pairs Shortest Paths) problem be solved by running an alread...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How can the APSP (_All-Pairs Shortest Paths_) problem be solved by running an already known single-source algorithm (which one?), and what is its computational complexity? #card

?
A first solution to the APSP problem consists in running the **Bellman-Ford** algorithm $|V|$ times, using each node of the graph in turn as the source.

**Complexity:**

- A single execution of Bellman-Ford takes $O(|V| \cdot |E|)$ time.
- Running it for all $|V|$ source nodes, the total cost is:

$$

O(|V|) \cdot O(|V| \cdot |E|) = O(|V|^2 |E|)

$$

📝 Example:
If the graph is dense, i.e., $|E| = \Theta(|V|^2)$, the complexity becomes $O(|V|^4)$, making it impractical for large graphs.

⚠️ Warning:
If the graph contained no edges with negative weight, one could run **Dijkstra's** algorithm for each node, achieving a complexity of $O(|V|^2 \log |V| + |V||E|)$.
📌 Note:
On dense or intermediate graphs, an approach based on dynamic programming (such as the Floyd-Warshall algorithm) allows reducing the time complexity to $O(|V|^3)$ regardless of the number of edges.
