---
title: "Exercise 2"
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
  - "Exercise 2"
---

# 🎴 Exercise 2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Exercise 2

Given a directed graph $G = (V, E)$ and assuming $n$ is the number of vertices in the graph, write an algorithm that determines, for each node, the in-degree and the out-degree.
Write two versions, one assuming the graph is represented using an adjacency matrix, and one using adjacency lists. Compute the computational cost of the functions.

_Hint:_ Store the node degrees using two arrays: $\textsf{IN}[1..n]$ for in-degree, $\textsf{OUT}[1..n]$ for out-degree. The output is a pair of arrays. #card
?
The algorithm stores the respective degrees of each node in two arrays $\textsf{IN}$ and $\textsf{OUT}$.

**(i) Graph $G$ represented via an $n \times n$ matrix:**
The out-degree of node $i$ is given by the number of 1s in the $i$-th row of the matrix; the in-degree by the number of 1s in the $i$-th column.

```text
Degree(G)
    IN[1..n] new array
    OUT[1..n] new array
    for i := 1 to n do
        IN[i] := 0
        OUT[i] := 0
    for i := 1 to n do
        for j := i + 1 to n do
            if G[i, j] = 1 then
                OUT[i] := OUT[i] + 1
                IN[j] := IN[j] + 1
            if G[j, i] = 1 then
                IN[i] := IN[i] + 1
                OUT[j] := OUT[j] + 1
    return (IN, OUT)
```

The computational cost is dominated by the two nested $\texttt{for}$ loops, which explore the upper triangular submatrix of $G$. The instructions executed within the body of the innermost $\texttt{for}$ run in constant time, so the computational cost of the algorithm is $O(n^2)$.

**(ii) Graph $G$ represented via adjacency lists:**
$G$ is an array of $n$ lists, $\textsf{G}[i]$ contains the identifiers of the neighbors of $i$.

```text
Degree(G)
    n := length(G)
    IN[1..n] new array
    OUT[1..n] new array
    for i := 1 to n do
        IN[i] := 0
        OUT[i] := 0
    for i := 1 to n do
        N := G[i]
        while N ≠q NIL do
            OUT[i] := OUT[i] + 1
            IN[N.val] := IN[N.val] + 1
            N := N.next
    return (IN, OUT)
```

The first $\texttt{for}$ costs $O(n)$. In the second $\texttt{for}$, the cost of assignments is $O(n)$, while all iterations of the $\texttt{while}$ loop traverse the neighbor lists performing a constant number of operations for each edge, costing $O(m)$. In total: $O(n) + O(n) + O(m) = O(n + m)$.

📌 Note:
The high-level formalizations below represent the two abstract strategies for computing degrees:

1. **Left (Edge scanning):** iterates directly over the set of edges $\textsf{E}$ (abstraction of an Edge List).
2. **Right (Adjacency scanning):** uses the adjacency array $\textsf{Adj}[\textsf{u}]$, of which the linked list version using pointers to $\texttt{(val,next)}$ elements (seen in point ii) represents the concrete implementation.

$\small\begin{array}{ll}
\textsf{Degree}(\textsf{G} = (\textsf{V}, \textsf{E})) & \\
\quad \textsf{IN}[1..|\textsf{V}|] \textsf{ new array of 0s} & \\
\quad \textsf{OUT}[1..|\textsf{V}|] \textsf{ new array of 0s} & \\
\quad \bbox[#D35400, 4px]{\begin{array}{l}
\texttt{for each } (\textsf{u}, \textsf{v}) \in \textsf{E} \texttt{ do} \\
\quad \textsf{OUT}[\textsf{u}] := \textsf{OUT}[\textsf{u}] + 1 \\
\quad \textsf{IN}[\textsf{v}] := \textsf{IN}[\textsf{v}] + 1
\end{array}} & \\
\quad \texttt{return } (\textsf{IN}, \textsf{OUT})
\end{array}$ $\small\begin{array}{ll}
\textsf{Degree}(\textsf{G} = (\textsf{V}, \textsf{E})) & \\
\quad \textsf{IN}[1..|\textsf{V}|] \textsf{ new array of 0s} & \\
\quad \textsf{OUT}[1..|\textsf{V}|] \textsf{ new array of 0s} & \\
\quad \bbox[#800080, 4px]{\begin{array}{l}
\texttt{for each } \textsf{u} \in \textsf{V} \texttt{ do} \\
\quad \bbox[#008080, 4px]{\begin{array}{l}
\texttt{for each } \textsf{v} \in \textsf{Adj}[\textsf{u}] \texttt{ do} \\
\quad \textsf{OUT}[\textsf{u}] := \textsf{OUT}[\textsf{u}] + 1 \\
\quad \textsf{IN}[\textsf{v}] := \textsf{IN}[\textsf{v}] + 1
\end{array}}
\end{array}} & \\
\quad \texttt{return } (\textsf{IN}, \textsf{OUT})
\end{array}$

⚠️ Warning:
In the left version (scanning over $\textsf{E}$), it is important not to nest `for each (u,v) in E` inside a `for each v in V` loop. This would force the algorithm to evaluate all $\vert{}\textsf{E}\vert{}$ elements for each of the $\vert{}\textsf{V}\vert{}$ nodes ($\vert{}\textsf{V}\vert{} \cdot \vert{}\textsf{E}\vert{}$ checks), even those not incident to the current node.
Not to mention that, iterating over the entire edge set $\textsf E$ for each vertex $\textsf v \in \textsf V$ without applying filters, the algorithm would erroneously increment the counters of each edge $\vert{}\textsf{V}\vert{}$ times, multiplying all degrees in the graph by $\vert{}\textsf{V}\vert{}$ (unless only edges incident to $\textsf v$ are filtered).
