---
title: "State the Safe Edge Theorem (Cut Theorem) for Minimum Spanning Trees."
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
  - "State the Safe Edge Theorem (Cut Theorem) for Minimum Spanning Trees."
---

# 🎴 State the Safe Edge Theorem (Cut Theorem) for Minimum Spanning Trees.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: State the Safe Edge Theorem (Cut Theorem) for Minimum Spanning Trees. #card

?
Given a connected undirected graph $G = (V, E)$ and a cost function $c : E \to \mathbb{R}$:

Let $(S, V \setminus S)$ be a cut of $G$ (with $S \subset V$ and $0 < |S| < |V|$), and let $e = (u,v) \in E$ be an edge of minimum cost crossing the cut (i.e., $u \in S$ and $v \in V \setminus S$).

**Claim:** Edge $e$ belongs to **at least one Minimum Spanning Tree (MST)** for $G$.

This theorem provides the theoretical foundation behind the correctness of all greedy algorithms for constructing MSTs (including Kruskal and Prim).
