---
title: "Exercise 6 (2)"
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
  - "Exercise 6 (2)"
---

# 🎴 Exercise 6 (2)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝📍 Exercise 6

Consider the DFS procedure running on the directed graphs shown in the figure below. Assuming that DFS iterates over the vertices in order (from 1 to $n = 8$) and that the adjacency lists are also sorted, determine the finishing times $\textsf{post}[1], \dots, \textsf{post}[n]$ computed by the procedure.

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




    (e)





    (f) #card

?
The finishing times $\textsf{post}[1..8]$ computed by the DFS procedure in the six cases are:

**(a)**
$\begin{gather*}\textsf{post}[1] = 4, \; \textsf{post}[2] = 8, \; \textsf{post}[3] = 16\\ \textsf{post}[4] = 10, \; \textsf{post}[5] = 15, \; \textsf{post}[6] = 3\\ \textsf{post}[7] = 14, \; \textsf{post}[8] = 7\end{gather*}$

**(b)**
$\begin{gather*}\textsf{post}[1] = 10, \; \textsf{post}[2] = 14, \; \textsf{post}[3] = 7\\ \textsf{post}[4] = 9, \; \textsf{post}[5] = 16, \; \textsf{post}[6] = 6\\ \textsf{post}[7] = 8, \; \textsf{post}[8] = 13\end{gather*}$

**(c)**
$\begin{gather*}\textsf{post}[1] = 6, \; \textsf{post}[2] = 5, \; \textsf{post}[3] = 4\\ \textsf{post}[4] = 14, \; \textsf{post}[5] = 10, \; \textsf{post}[6] = 11\\ \textsf{post}[7] = 13, \; \textsf{post}[8] = 16\end{gather*}$

**(d)**
$\begin{gather*}\textsf{post}[1] = 14, \; \textsf{post}[2] = 12, \; \textsf{post}[3] = 9\\ \textsf{post}[4] = 11, \; \textsf{post}[5] = 8, \; \textsf{post}[6] = 3\\ \textsf{post}[7] = 13, \; \textsf{post}[8] = 16\end{gather*}$

**(e)**
$\begin{gather*}\textsf{post}[1] = 6, \; \textsf{post}[2] = 10, \; \textsf{post}[3] = 3\\ \textsf{post}[4] = 14, \; \textsf{post}[5] = 13, \; \textsf{post}[6] = 5\\ \textsf{post}[7] = 16, \; \textsf{post}[8] = 9\end{gather*}$

**(f)**
$\begin{gather*}\textsf{post}[1] = 6, \; \textsf{post}[2] = 14, \; \textsf{post}[3] = 13\\ \textsf{post}[4] = 16, \; \textsf{post}[5] = 12, \; \textsf{post}[6] = 3\\ \textsf{post}[7] = 11, \; \textsf{post}[8] = 5\end{gather*}$
