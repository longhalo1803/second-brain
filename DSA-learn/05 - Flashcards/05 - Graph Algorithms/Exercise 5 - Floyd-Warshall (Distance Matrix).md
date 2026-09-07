---
title: "Exercise 5 - Floyd-Warshall (Distance Matrix)"
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
  - "Exercise 5 - Floyd-Warshall (Distance Matrix)"
---

# 🎴 Exercise 5 - Floyd-Warshall (Distance Matrix)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝📍 Exercise 5 - Floyd-Warshall (Distance Matrix)

For the directed and weighted graphs shown below, compute the distance matrix $d(i,j,k)$ computed by the Floyd-Warshall algorithm for all possible pairs of vertices $i, j$ and for the value of $k$ indicated in the captions.

    (a) $k = 3$




    (b) $k = 2$




    (c) $k = 2$




    (d) $k = 3$




    (e) $k = 4$




    (f) $k = 5$ #card

?
Distance matrices $d(i,j,k)$ computed by the Floyd-Warshall algorithm:

    **(a) $k = 3$**

$$

\begin{pmatrix}0 & 3 & 1 & 6 & 3 \\6 & 0 & 7 & 12 & 9 \\12 & 6 & 0 & 5 & 2 \\18 & 12 & 6 & 0 & 8 \\\infty & \infty & \infty & \infty & 0\end{pmatrix}

$$

    **(b) $k = 2$**

$$

\begin{pmatrix}0 & \infty & 1 & \infty & \infty \\3 & 0 & 4 & 5 & \infty \\7 & 4 & 0 & 1 & 1 \\7 & 4 & 3 & 0 & 1 \\\infty & \infty & \infty & 6 & 0\end{pmatrix}

$$

    **(c) $k = 2$**

$$

\begin{pmatrix}0 & \infty & 4 & \infty & \infty \\4 & 0 & 8 & 5 & \infty \\1 & 3 & 0 & 8 & 4 \\\infty & \infty & \infty & 0 & 1 \\\infty & \infty & 5 & \infty & 0\end{pmatrix}

$$

    **(d) $k = 3$**

$$

\begin{pmatrix}0 & 1 & 4 & 10 & \infty \\5 & 0 & 3 & 9 & \infty \\2 & 3 & 0 & 6 & \infty \\10 & 5 & 8 & 0 & 5 \\7 & 8 & 5 & 1 & 0\end{pmatrix}

$$

    **(e) $k = 4$**

$$

\begin{pmatrix}0 & 2 & 6 & 8 & \color{#D9534F}{9} & 3 \\\infty & 0 & 4 & 6 & \color{#D9534F}{7} & 1 \\\infty & \infty & 0 & 2 & \color{#D9534F}{3} & \infty \\\infty & \infty & \infty & 0 & 1 & \infty \\3 & 5 & 9 & 11 & 0 & 6 \\\infty & \infty & -2 & 0 & \color{#D9534F}{1} & 0\end{pmatrix}

$$

    **(f) $k = 5$**

$$

\begin{pmatrix}0 & 3 & 8 & 3 & -4 \\3 & 0 & 11 & 1 & -1 \\-3 & 0 & 0 & -5 & -7 \\2 & 5 & 10 & 0 & -2 \\8 & 11 & 16 & 6 & 0\end{pmatrix}

$$
