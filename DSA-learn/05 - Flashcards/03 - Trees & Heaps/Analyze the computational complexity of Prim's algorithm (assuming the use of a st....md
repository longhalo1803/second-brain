---
title: "Analyze the computational complexity of Prim's algorithm (assuming the use of a st..."
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
  - "Analyze the computational complexity of Prim's algorithm (assuming the use of a st..."
---

# 🎴 Analyze the computational complexity of Prim's algorithm (assuming the use of a st...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Analyze the computational complexity of Prim's algorithm (assuming the use of a standard Min-Heap). #card

?

- **Array initialization and allocation:** $O(|V|)$.
- **Priority Queue Construction (`make_priority_queue`):** $O(|V|)$.
- **Extracting the minimum (`DeQueue`):** executed $|V|$ times. Each extraction from a Min-Heap requires $O(\log |V|)$ $\implies$ total $O(|V| \log |V|)$.
- **Priority update (`Decrease_Priority`):** executed at most once per edge for each direction, i.e., at most $O(|E|)$ times in total. Each update in the Min-Heap requires $O(\log |V|)$ $\implies$ total $O(|E| \log |V|)$.$\small
  \begin{array}{ll}\textsf{Prim(G = (V, E), c)} & \\\quad \texttt{for all } \textsf{v} \in V \texttt{ do} & \color{#D9534F}{O(|V|)} \\\quad\quad \textsf{cost[v] := } +\infty & \\\quad\quad \textsf{prev[v] := NIL} & \\\quad\quad \textsf{S[v] := 0} & \\\quad \textsf{choose a source node } \textsf{s} \in V & \color{#D9534F}{O(1)} \\\quad \textsf{cost[s] := 0} & \\\quad \textsf{S[s] := 1} & \\\quad \textsf{Q := make_priority_queue(\{(v, cost[v]) } \mid \textsf{ v} \in V\textsf{\})} & \color{#D9534F}{O(|V|)} \\\quad \texttt{while NOT } \textsf{is_empty_queue(Q)} \texttt{ do} & \small\textsf{// executed } |V| \textsf{ times} \\\quad\quad \textsf{u := DeQueue(Q)} & \color{#D9534F}{O(\log |V|)} \\\quad\quad \textsf{S[u] := 1} & \\\quad\quad \texttt{for all } (u,v) \in E \texttt{ do} & \\\quad\quad\quad \texttt{if } \textsf{S[v] = 0 AND cost[v] > c(u,v)} \texttt{ then} & \\\quad\quad\quad\quad \textsf{cost[v] := c(u,v)} & \\\quad\quad\quad\quad \textsf{prev[v] := u} & \\\quad\quad\quad\quad \textsf{Decrease_Priority(Q, v, cost[v])} & \color{#D9534F}{O(\log |V|)} \\\quad \texttt{return } \textsf{prev[]} &\end{array}$

**Total Complexity:**

$$

O(|V|) + O(|V| \log |V|) + O(|E| \log |V|) = O(|E| \log |V|)

$$

📌 **Advanced note:**
If a priority queue implemented via a **Fibonacci Heap** is used, `Decrease_Priority` takes $O(1)$ amortized time, reducing the total complexity of Prim's algorithm to:

$$

O(|E| + |V| \log |V|)

$$
