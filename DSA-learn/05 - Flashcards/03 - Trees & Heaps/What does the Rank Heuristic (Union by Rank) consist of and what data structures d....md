---
title: "What does the Rank Heuristic (Union by Rank) consist of and what data structures d..."
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
  - "What does the Rank Heuristic (Union by Rank) consist of and what data structures d..."
---

# 🎴 What does the Rank Heuristic (Union by Rank) consist of and what data structures d...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What does the **Rank Heuristic** (Union by Rank) consist of and what data structures does it use? #card

?
The **Rank Heuristic** (_Union by Rank_) is a structural optimization technique that aims to keep the height of the trees in the forest small.

During a `Union` operation between two sets with distinct roots, **the shorter tree** (with smaller rank)** is attached as a subtree of the root of the taller tree** (with larger rank).
If the two trees have the same rank, a root is chosen arbitrarily and its rank is incremented by 1.

**Required data structures**:

1. `DS.p[1..n]`: Parent array.
2. `DS.rank[1..n]`: Array storing the height (or rank) of the tree rooted at the corresponding node.

---
