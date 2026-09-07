---
title: "How does the Adjacency Lists representation work and what are its complexities"
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
  - "How does the Adjacency Lists representation work and what are its complexities"
---

# 🎴 How does the Adjacency Lists representation work and what are its complexities

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How does the **Adjacency Lists representation** work and what are its complexities? #card

?
An array $G[1..n]$ of linked lists, where each element $G[v]$ is a pointer to the list containing all the neighbors of node $v$.

📝 Examples:

      undirected










      directed

**Complexity:**
• Space/memory usage: $\Theta(|V| + |E|) = \Theta(n + m)$
• Edge presence check $(u,v)$: $O(\text{length of list } G[u]) = O(\text{deg}(u))$
• Listing neighbors of node $v$: $\Theta(\text{length of list } G[v]) = \Theta(\text{deg}(v))$.

📝 Examples of graph representation using an adjacency list:

⚠️ Warning:
`G` is an array whose index $x$ represents the source node (e.g., `G[1]` for node 1, `G[2]` for node 2).
`G[x]` does not contain the numerical value of node $x$, but a pointer to the head of the linked list containing all adjacent nodes (that is, the targets of edges outgoing from $x$).
