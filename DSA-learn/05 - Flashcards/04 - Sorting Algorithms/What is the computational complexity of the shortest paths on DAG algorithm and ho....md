---
title: "What is the computational complexity of the shortest paths on DAG algorithm and ho..."
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
  - "What is the computational complexity of the shortest paths on DAG algorithm and ho..."
---

# 🎴 What is the computational complexity of the shortest paths on DAG algorithm and ho...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the **computational complexity** of the shortest paths on DAG algorithm and how is it analyzed? #card

?
The total time complexity is **$O(|V| + |E|)$**.

**Detailed analysis:**

- **Topological Sort:** $O(|V| + |E|)$.
- **Array dist initialization:** $O(|V|)$.
- **Discarding unreachable nodes:** at most $O(|V|)$.
- **Main while loop:** each node is popped from the stack only once ($O(|V|)$ iterations). For each node $v$, all of its incoming edges $(u,v)$ are examined. Summing over all nodes, each edge of the graph is considered exactly once, for a total of **$O(|E|)$** operations.📌 Note: the cost is linear with respect to the size of the graph, outperforming generic algorithms like Dijkstra $O(|E| + |V| \log |V|)$ thanks to the acyclic structure of the DAG.

$\small\begin{array}{ll}
\textsf{Shortest_Path_DAG(G=(V,E), } \textcolor{#FF8C00}{\textsf{c}}\textsf{, } \textcolor{#E65100}{\textsf{s}}\textsf{)} & \\
\quad \textcolor{#00AA00}{\textsf{TS := Topological_sort(G)}} & \small{\textsf{// Returns a stack}} \\
\quad \texttt{for all } \textsf{v} \in \textsf{V} \texttt{ do} & \\
\quad\quad \textcolor{#00AAFF}{\textsf{dist}\texttt{[}\textsf{v}\texttt{]} \textsf{:= } +\infty} & \\
\quad \textcolor{#00AAFF}{\textsf{dist}\texttt{[}}\textcolor{#E65100}{\textsf{s}}\textcolor{#00AAFF}{\texttt{]} \textsf{:= } 0} & \\
\quad \textcolor{#00AA00}{\textsf{v := pop(TS)}} & \\
\quad \texttt{while } \textsf{v} \neq \textcolor{#E65100}{\textsf{s}} \texttt{ do} & \small{\textsf{// Nodes preceding s are not reachable from s}} \\
\quad\quad \textcolor{#00AA00}{\textsf{v := pop(TS)}} & \small{\textsf{// At the end of the while loop v = s (dist[s] is already 0)}} \\
\quad \texttt{while NOT } \textsf{is_empty(TS)} \texttt{ do} & \\
\quad\quad \textcolor{#00AA00}{\textsf{v := pop(TS)}} & \small{\textsf{// Starts from the node following s in topological order}} \\
\quad\quad \textcolor{#00AAFF}{\textsf{dist}\texttt{[}\textsf{v}\texttt{]} \textsf{:= } \min\limits_{(u,v) \in E} \{\textsf{dist}\texttt{[}\textsf{u}\texttt{]} + } \textcolor{#FF8C00}{\textsf{c(u,v)}}\textcolor{#00AAFF}{\textsf{\}}} & \small{\textsf{// Relaxation over incoming edges to v}} \\
\quad \texttt{return } \textcolor{#00AAFF}{\textsf{dist}\texttt{[]}} &
\end{array}$,
