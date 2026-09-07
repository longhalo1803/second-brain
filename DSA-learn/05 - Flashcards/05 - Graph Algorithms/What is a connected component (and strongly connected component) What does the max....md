---
title: "What is a connected component (and strongly connected component) What does the max..."
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
  - "What is a connected component (and strongly connected component) What does the max..."
---

# 🎴 What is a connected component (and strongly connected component) What does the max...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 What is a connected component (and strongly connected component)? What does the maximality property indicate?

📝 Examples:
In the following _undirected_ graph, is the highlighted subset a **connected component**?

In the following _directed_ graph, is the highlighted subset a **connected component**?

In the following _directed_ graph, is the highlighted subset a **strongly connected component**? #card
?
A _connected component_ (or _strongly connected component_ for directed graphs) is a connected subgraph $G'=(V',E')$ of $G$ that satisfies the **maximality** property, meaning that $G'$ is not contained in any larger connected subgraph of $G$.
That is, it is not possible to add other nodes or edges of the original graph to it while maintaining the connectivity property (= the ability to reach any node starting from another).

.tooltip {
position: relative;
display: inline-block;
cursor: pointer;
}

.tooltip::after {
content: attr(data-tooltip);
position: absolute;
bottom: 125%;
left: 50%;
transform: translateX(-50%) translateY(5px);
background-color: #333;
color: #fff;
padding: 6px 10px;
border-radius: 4px;
font-size: 13px;
white-space: normal;
width: 180px;
text-align: center;
opacity: 0;
visibility: hidden;
transition: opacity 0.2s ease, transform 0.2s ease;
pointer-events: none;
z-index: 100;
font-weight: normal;
line-height: 1.3;
}

.tooltip::before {
content: '';
position: absolute;
bottom: 115%;
left: 50%;
transform: translateX(-50%) translateY(5px);
border-width: 5px;
border-style: solid;
border-color: #333 transparent transparent transparent;
opacity: 0;
visibility: hidden;
transition: opacity 0.2s ease, transform 0.2s ease;
pointer-events: none;
z-index: 100;
}

.tooltip:hover::after,
.tooltip:hover::before,
.tooltip:focus-visible::after,
.tooltip:focus-visible::before {
opacity: 1;
visibility: visible;
transform: translateX(-50%) translateY(0);
}

📝 Examples (hover over the answer for a detailed explanation):
In the following _undirected_ graph, is the highlighted subset a **connected component**?

In the following _directed_ graph, is the highlighted subset a **connected component**?

In the following _directed_ graph, is the highlighted subset a **strongly connected component**?
