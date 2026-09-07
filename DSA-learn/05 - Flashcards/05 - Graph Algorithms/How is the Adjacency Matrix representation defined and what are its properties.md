---
title: "How is the Adjacency Matrix representation defined and what are its properties"
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
  - "How is the Adjacency Matrix representation defined and what are its properties"
---

# 🎴 How is the Adjacency Matrix representation defined and what are its properties

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How is the **Adjacency Matrix representation** defined and what are its properties? #card

?
Representation using a matrix $G$ of size $n \times n$ (with nodes numbered from $1$ to $n$):

$$
G[i,j] = \begin{cases} 1 & \text{if } \exists (i,j) \in E \\ 0 & \text{otherwise} \end{cases}
$$

$i$ row index, $j$ column index.
The matrix is symmetric ($G[i,j]=G[j,i]$) if and only if the graph is _undirected_.

📝 Examples:

    undirected



    G[i, j]




        1
        2
        3
        4


        1
        0
        1
        1
        0


        2
        1
        0
        1
        1


        3
        1
        1
        0
        1


        4
        0
        1
        1
        0







    directed



    G[i, j]




        1
        2
        3
        4


        1
        0
        1
        1
        0


        2
        0
        0
        0
        1


        3
        0
        1
        0
        0


        4
        0
        1
        1
        0

**Complexity:**
• Space/memory usage: $\Theta(n^2)$
• Edge presence check $(i,j)$: $\Theta(1)$
• Listing neighbors of node $i$: $\Theta(n)$

See also https://thepalindrome.org/p/matrices-and-graphs

Note that, for example, the first row of the matrix corresponds to the outgoing edges (with weights) from the first node (0 if that edge does not exist) and the first column corresponds to the incoming edges to the first node.
