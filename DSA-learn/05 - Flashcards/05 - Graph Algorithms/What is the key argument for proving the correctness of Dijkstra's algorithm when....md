---
title: "What is the key argument for proving the correctness of Dijkstra's algorithm when..."
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
  - "What is the key argument for proving the correctness of Dijkstra's algorithm when..."
---

# 🎴 What is the key argument for proving the correctness of Dijkstra's algorithm when...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the key argument for proving the correctness of Dijkstra's algorithm when a node enters the Settled World? #card

?
**Correctness property:**
When a node $u$ with minimum $\textsf{dist}[u]$ among the nodes in the Frontier is extracted and enters the **Settled World**, the value $\textsf{dist}[u]$ holds exactly the **true shortest distance** $\delta(s, u)$ from the source.

**Proof that finding a shorter path is impossible:**
Could there exist another path from $s$ to $u$ with a total cost strictly less than $\textsf{dist}[u]$?

- **Arriving from the Settled World?** NO, because all nodes in the Settled World have already been explored and all their outgoing edges have already been relaxed.
- **Arriving from the Frontier (passing through another node $v$)?** NO, because $u$ was specifically chosen as the node with minimum distance in the Frontier, so $\textsf{dist}[v] \geq \textsf{dist}[u]$. Since edge weights are non-negative ($c(e) \geq 0$), adding further edges gives $\textsf{dist}[v] + c(v, \dots, u) \geq \textsf{dist}[u]$.
- **Arriving from the Far World?** NO, because any path to the Far World must first pass through a node in the Frontier, falling back into the previous case.
  ⚠️ **Warning:** this proof relies fundamentally on the assumption that edge weights are **non-negative** ($c(e) \geq 0$).

#slide-tab-1:checked ~ div label[for='slide-tab-1'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-1:checked ~ div .slide-content-1 { display: block !important; }
#slide-tab-2:checked ~ div label[for='slide-tab-2'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-2:checked ~ div .slide-content-2 { display: block !important; }
#slide-tab-3:checked ~ div label[for='slide-tab-3'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-3:checked ~ div .slide-content-3 { display: block !important; }
#slide-tab-4:checked ~ div label[for='slide-tab-4'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-4:checked ~ div .slide-content-4 { display: block !important; }
#slide-tab-5:checked ~ div label[for='slide-tab-5'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-5:checked ~ div .slide-content-5 { display: block !important; }
#slide-tab-6:checked ~ div label[for='slide-tab-6'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-6:checked ~ div .slide-content-6 { display: block !important; }
#slide-tab-7:checked ~ div label[for='slide-tab-7'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-7:checked ~ div .slide-content-7 { display: block !important; }
#slide-tab-8:checked ~ div label[for='slide-tab-8'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-8:checked ~ div .slide-content-8 { display: block !important; }
#slide-tab-9:checked ~ div label[for='slide-tab-9'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-9:checked ~ div .slide-content-9 { display: block !important; }
#slide-tab-10:checked ~ div label[for='slide-tab-10'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-10:checked ~ div .slide-content-10 { display: block !important; }
#slide-tab-11:checked ~ div label[for='slide-tab-11'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-11:checked ~ div .slide-content-11 { display: block !important; }
#slide-tab-12:checked ~ div label[for='slide-tab-12'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-12:checked ~ div .slide-content-12 { display: block !important; }
#slide-tab-13:checked ~ div label[for='slide-tab-13'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-13:checked ~ div .slide-content-13 { display: block !important; }
#slide-tab-14:checked ~ div label[for='slide-tab-14'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-14:checked ~ div .slide-content-14 { display: block !important; }
#slide-tab-15:checked ~ div label[for='slide-tab-15'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-15:checked ~ div .slide-content-15 { display: block !important; }
#slide-tab-16:checked ~ div label[for='slide-tab-16'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-16:checked ~ div .slide-content-16 { display: block !important; }
#slide-tab-17:checked ~ div label[for='slide-tab-17'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-17:checked ~ div .slide-content-17 { display: block !important; }
#slide-tab-18:checked ~ div label[for='slide-tab-18'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-18:checked ~ div .slide-content-18 { display: block !important; }
#slide-tab-19:checked ~ div label[for='slide-tab-19'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-19:checked ~ div .slide-content-19 { display: block !important; }
#slide-tab-20:checked ~ div label[for='slide-tab-20'] { background: currentColor; color: #fff; opacity: 1; font-weight: bold; }
#slide-tab-20:checked ~ div .slide-content-20 { display: block !important; }

1234567891011121314151617181920
