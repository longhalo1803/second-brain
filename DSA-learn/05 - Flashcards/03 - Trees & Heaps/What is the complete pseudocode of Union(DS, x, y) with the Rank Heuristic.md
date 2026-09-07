---
title: "What is the complete pseudocode of Union(DS, x, y) with the Rank Heuristic"
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
  - "What is the complete pseudocode of Union(DS, x, y) with the Rank Heuristic"
---

# 🎴 What is the complete pseudocode of Union(DS, x, y) with the Rank Heuristic

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the complete pseudocode of `Union(DS, x, y)` with the Rank Heuristic? #card

?
The three-way `Union` operation based on the ranks of the roots is implemented as follows:

```text
Union(DS, x, y)
    xr := Find-set(DS, x)
    yr := Find-set(DS, y)
    if xr ≠q yr then
        if {#00a2ff}{DS.rank[xr]} > {#00a2ff}{DS.rank[yr]} then
            {#f74040}{DS.p[yr]} := xr            // {#D9534F}{≤ftarrow tree yr (shorter) becomes subtree of xr}
        else
            {#f74040}{DS.p[xr]} := yr            // {#D9534F}{≤ftarrow tree xr becomes subtree of yr}
            if {#00a2ff}{DS.rank[xr]} = {#00a2ff}{DS.rank[yr]} then
                {#00a2ff}{DS.rank[yr]} := {#00a2ff}{DS.rank[yr]} + 1 // {#D9534F}{≤ftarrow if ranks are equal, increment rank of yr}
```

**Computational cost**: $O(\textsf{rank}[\text{representative of } x] + \textsf{rank}[\text{representative of } y])$.
