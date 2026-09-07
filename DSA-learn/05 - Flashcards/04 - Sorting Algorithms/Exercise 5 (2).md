---
title: "Exercise 5 (2)"
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
  - "Exercise 5 (2)"
---

# 🎴 Exercise 5 (2)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝📍 Exercise 5

Consider the DFS procedure running on the directed graphs shown in the figure below. Assuming that DFS iterates over the vertices in order (from 1 to $n = 8$) and that the adjacency lists are also sorted, determine the type assigned to each edge (i.e., whether it is a tree, back, forward, or cross edge).

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
Here is the edge classification for each of the graphs (a)-(f):

    **(a)**

    $(1,2) \rightarrow Tree$

    $(2,1) \rightarrow Back$

    $(2,6) \rightarrow Tree$

    $(3,8) \rightarrow Cross$

    $(3,4) \rightarrow Tree$

    $(4,3) \rightarrow Back$

    $(5,1) \rightarrow Back$

    $(5,2) \rightarrow Back$

    $(6,2) \rightarrow Back$

    $(6,7) \rightarrow Tree$

    $(7,8) \rightarrow Tree$

    $(7,2) \rightarrow Back$

    $(7,5) \rightarrow Tree$


    **(b)**

    $(1,8) \rightarrow Tree$

    $(1,3) \rightarrow Tree$

    $(2,4) \rightarrow Tree$

    $(3,2) \rightarrow Tree$

    $(4,7) \rightarrow Tree$

    $(5,1) \rightarrow Back$

    $(6,4) \rightarrow Back$

    $(6,5) \rightarrow Cross$

    $(7,5) \rightarrow Tree$

    $(7,6) \rightarrow Tree$


    **(c)**

    $(1,2) \rightarrow Tree$

    $(2,4) \rightarrow Tree$

    $(2,5) \rightarrow Forward$

    $(3,8) \rightarrow Forward$

    $(3,4) \rightarrow Back$

    $(3,7) \rightarrow Tree$

    $(4,1) \rightarrow Back$

    $(4,5) \rightarrow Tree$

    $(5,2) \rightarrow Back$

    $(5,3) \rightarrow Tree$

    $(6,8) \rightarrow Cross$

    $(6,2) \rightarrow Cross$

    $(7,8) \rightarrow Tree$

    $(7,1) \rightarrow Back$


    **(d)**

    $(1,3) \rightarrow Tree$

    $(2,1) \rightarrow Back$

    $(2,5) \rightarrow Back$

    $(3,5) \rightarrow Tree$

    $(3,6) \rightarrow Tree$

    $(3,7) \rightarrow Forward$

    $(4,5) \rightarrow Cross$

    $(4,6) \rightarrow Cross$

    $(5,8) \rightarrow Tree$

    $(5,7) \rightarrow Tree$

    $(6,5) \rightarrow Cross$

    $(6,7) \rightarrow Cross$

    $(7,1) \rightarrow Back$

    $(7,2) \rightarrow Tree$


    **(e)**

    $(1,3) \rightarrow Tree$

    $(2,8) \rightarrow Tree$

    $(3,2) \rightarrow Tree$

    $(3,7) \rightarrow Tree$

    $(4,2) \rightarrow Cross$

    $(4,3) \rightarrow Cross$

    $(5,3) \rightarrow Cross$

    $(5,4) \rightarrow Cross$

    $(5,6) \rightarrow Tree$

    $(6,7) \rightarrow Cross$

    $(7,2) \rightarrow Cross$


    **(f)**

    $(1,2) \rightarrow Tree$

    $(1,4) \rightarrow Forward$

    $(1,6) \rightarrow Forward$

    $(2,8) \rightarrow Forward$

    $(2,6) \rightarrow Tree$

    $(3,4) \rightarrow Cross$

    $(3,5) \rightarrow Tree$

    $(3,7) \rightarrow Forward$

    $(5,2) \rightarrow Cross$

    $(5,7) \rightarrow Tree$

    $(6,8) \rightarrow Tree$

    $(6,2) \rightarrow Back$

    $(6,4) \rightarrow Tree$

    $(7,3) \rightarrow Back$
