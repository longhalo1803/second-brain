---
title: "How are high-level iterations over nodes and edges of a graph expressed"
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
  - "How are high-level iterations over nodes and edges of a graph expressed"
---

# 🎴 How are high-level iterations over nodes and edges of a graph expressed

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How are high-level iterations over nodes and edges of a graph expressed? #card

?
Given a graph $G=(V,E)$:

**1) Iterate over all nodes:**
$\begin{array}{l} \texttt{for all } \textsf{v} \in \textsf{V} \texttt{ do} \\ \quad \small\textsf{... instructions for node v} \end{array}$

**2) Iterate over all edges:**
$\begin{array}{l} \texttt{for all } (\textsf{u}, \textsf{v}) \in \textsf{E} \texttt{ do} \\ \quad \small\textsf{... instructions for edge (u,v)} \end{array}$

**3) Iterate over all nodes and their incident edges:**
$\begin{array}{l} \texttt{for all } \textcolor{red}{\textsf{v}} \in \textsf{V} \texttt{ do} \\ \quad \small\textsf{... instructions for node v} \\ \quad \texttt{for all } (\textcolor{red}{\textsf{v}}, \textsf{u}) \in \textsf{E} \texttt{ do} \\ \quad\quad \small\textsf{... instructions for edge (v,u)} \end{array}$

📌 Note:
The traversal order of nodes and edges is not predetermined.
For undirected graphs the pair $(v,u)$ is unordered, while for directed graphs edges outgoing from $v$ are traversed.
