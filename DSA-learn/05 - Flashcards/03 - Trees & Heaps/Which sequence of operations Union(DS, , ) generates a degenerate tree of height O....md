---
title: "Which sequence of operations Union(DS, , ) generates a degenerate tree of height O..."
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
  - "Which sequence of operations Union(DS, , ) generates a degenerate tree of height O..."
---

# 🎴 Which sequence of operations Union(DS, , ) generates a degenerate tree of height O...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Which sequence of operations `Union(DS, ?, ?)` generates a degenerate tree of height $\Omega(n)$ in the basic version, assuming that `Make-set()` is performed initially on 10 nodes from 1 to 10? #card

?
Without balancing heuristics, the following sequence of `Union` operations creates a unilinear chain (degenerate tree) of height $n-1$:

1. `Make-set(X)` on $X=\{1, 2, \dots, n\}$
2. `Union(DS, 1, 2)` $\implies$ the parent of 1 becomes 2.
3. `Union(DS, 1, 3)` $\implies$ `Find-set(1)` returns 2, so the parent of 2 becomes 3.
4. `Union(DS, 1, 4)` $\implies$ `Find-set(1)` returns 3, the parent of 3 becomes 4.
   $\dots$
   k. `Union(DS, 1, k)` $\implies$ the parent of $k-1$ becomes $k$.

⚠️ Warning:
In this chain-like tree, every `Find-set(DS, 1)` operation must traverse the entire chain, requiring $\Omega(n)$ time.

(_Note the error at minute 8:00 in the video above: the parent of root y is set to root x, so a chain shouldn't form, they should all point to 0. To actually produce a worst-case chain, the arguments must be reversed: union(1,0), union(2,1), union(3,2)..._)
