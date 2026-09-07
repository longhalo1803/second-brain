---
title: "For each of the cases, illustrate graphically the state of a disjoint-set data str..."
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
  - "For each of the cases, illustrate graphically the state of a disjoint-set data str..."
---

# 🎴 For each of the cases, illustrate graphically the state of a disjoint-set data str...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝📍 For each of the cases, illustrate graphically the state of a disjoint-set data structure on the set `X = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}` following the sequence of operations. Assume that, when two nodes have equal rank, the union uses the node with the higher number as the root.

⚠️ Note:
In the handling of disjoint-set operations, the choice of the new root in the event of a tie in rank may follow different conventions: in this formulation, it is deterministically established to choose the node with the higher numerical identifier, rather than relying on parameter order (left or right).
Moreover, initialization operations can be presented as individual calls to `makeset(x)` for each element or via a single overall call `makeset({1, 2, ..., n})`.
Such formal variations do not alter the underlying logic of the data structure in any way.

$$
\begin{array}{c c c}
\begin{array}{c}
\mathrm{makeset}(1), \dots, \mathrm{makeset}(10) \\
\mathrm{union}(6, 7) \\
\mathrm{union}(7, 4) \\
\mathrm{union}(6, 7) \\
\mathrm{find}(4) \\
\mathrm{union}(8, 5) \\[1.5em]
\text{(a)}
\end{array}
& \hspace{4em} &
\begin{array}{c}
\mathrm{makeset}(1), \dots, \mathrm{makeset}(10) \\
\mathrm{union}(6, 10) \\
\mathrm{union}(1, 10) \\
\mathrm{union}(2, 10) \\
\mathrm{find}(5) \\
\mathrm{union}(2, 1) \\[1.5em]
\text{(b)}
\end{array} \\[2.5em]
\begin{array}{c}
\mathrm{makeset}(1), \dots, \mathrm{makeset}(10) \\
\mathrm{union}(6, 7) \\
\mathrm{union}(7, 4) \\
\mathrm{union}(6, 7) \\
\mathrm{find}(4) \\
\mathrm{union}(8, 5) \\[1.5em]
\text{(c)}
\end{array}
& &
\begin{array}{c}
\mathrm{makeset}(1), \dots, \mathrm{makeset}(10) \\
\mathrm{union}(1, 10) \\
\mathrm{union}(4, 2) \\
\mathrm{union}(4, 1) \\
\mathrm{find}(9) \\
\mathrm{union}(8, 4) \\[1.5em]
\text{(d)⭐}
\end{array}
\end{array}
$$

$$
\begin{array}{c c c c c}
\begin{array}[b]{c}
\mathrm{makeset}(1), \dots, \mathrm{makeset}(10) \\
\mathrm{union}(8, 1) \\
\mathrm{union}(8, 6) \\
\mathrm{union}(10, 4) \\
\mathrm{find}(1) \\
\mathrm{union}(10, 1) \\
\mathrm{union}(2, 8) \\[1.5em]
\text{(e)⭐}
\end{array}
& \hspace{3em} &
\begin{array}[b]{c}
\mathrm{makeset}(1), \dots, \mathrm{makeset}(10) \\
\mathrm{union}(2, 1) \\
\mathrm{find}(10) \\
\mathrm{union}(5, 3) \\
\mathrm{union}(2, 8) \\
\mathrm{union}(9, 3) \\
\mathrm{find}(10) \\[1.5em]
\text{(f)⭐}
\end{array}
& \hspace{3em} &
\begin{array}[b]{c}
\mathrm{makeset}(1), \dots, \mathrm{makeset}(10) \\
\mathrm{union}(7, 1) \\
\mathrm{union}(9, 8) \\
\mathrm{union}(9, 1) \\
\mathrm{union}(5, 2) \\
\mathrm{union}(10, 2) \\
\mathrm{union}(9, 6) \\
\mathrm{find}(5) \\[1.5em]
\text{(g)⭐}
\end{array}
\end{array}
$$ #card
?
(a)

 (b)

 (c)

 (d)

 (e)

 (f)

 (g)
$$
