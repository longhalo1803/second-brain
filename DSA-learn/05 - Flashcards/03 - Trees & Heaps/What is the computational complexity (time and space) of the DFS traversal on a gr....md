---
title: "What is the computational complexity (time and space) of the DFS traversal on a gr..."
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
  - "What is the computational complexity (time and space) of the DFS traversal on a gr..."
---

# 🎴 What is the computational complexity (time and space) of the DFS traversal on a gr...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the computational complexity (time and space) of the DFS traversal on a graph G=(V,E) and how is it calculated? #card

?
**Time complexity:** $\Theta(|V| + |E|)$

**Proof:**

Code$\small \begin{array}{ll}
\bbox[#2563eb, 3pt]{\scriptsize\color{white}\textsf{Main procedure}} & \\
\textsf{DFS(G)} & \\
\quad \textsf{visited}\texttt{[0..n]} \textsf{ new array} & \\
\quad \texttt{for all } \textsf{v} \in \textsf{V} \texttt{ do} & \\
\quad\quad \textsf{visited}\texttt{[}\textsf{v}\texttt{]} \textsf{:= FALSE} & \\
\quad \texttt{for all } \textsf{v} \in \textsf{V} \texttt{ do} & \\
\quad\quad \texttt{if } \textsf{visited}\texttt{[}\textsf{v}\texttt{]} = \textsf{FALSE} \texttt{ then} & \\
\quad\quad\quad \textsf{DFS-Visit(G, v)} & \\
& \\
\bbox[#059669, 3pt]{\scriptsize\color{white}\textsf{Recursive procedure}} & \\
\textsf{DFS-Visit(G, v)} & \\
\quad \textsf{visited}\texttt{[}\textsf{v}\texttt{]} \textsf{:= TRUE} & \\
\quad \small\textsf{// examine node v (pre-visit case)} & \\
\quad \texttt{for all } (\textsf{v}, \textsf{u}) \in \textsf{E} \texttt{ do} \quad \small\textsf{// edges incident to v} \\
\quad\quad \texttt{if } \textsf{visited}\texttt{[}\textsf{u}\texttt{]} = \textsf{FALSE} \texttt{ then} & \\
\quad\quad\quad \textsf{DFS-Visit(G, u)} & \\
\quad \small\textsf{// examine node v (post-visit case)} &
\end{array}$

- **Initialization and main loop in `DFS(G)`:** Takes $O(|V|)$ time to initialize the `visited` array and iterate through all nodes.
- **Recursive calls `DFS-Visit(G, v)`:** Executed exactly **once** for each node $v \in V$ (thanks to the check on `visited[v]`).
- **Edge exploration:** Inside `DFS-Visit(G, v)`, the algorithm examines all edges incident to $v$, taking time proportional to the degree of the node $deg(v)$. Summing over all nodes:

$$

\sum\_{v \in V} deg(v) = 2|E| \in O(|E|)

$$

In total, the time complexity is:

$$

\begin{aligned} T(|V|, |E|) &= O(|V|) + \sum\_{v \in V} O(deg(v)) \\ &= O(|V|) + O(|E|) = \Theta(|V| + |E|) \end{aligned}

$$

**Space complexity:** $O(|V|)$
Due to the space for the `visited[0..n]` array and the maximum depth of the recursion stack (which in the worst case of a linear path graph is $O(|V|)$).
