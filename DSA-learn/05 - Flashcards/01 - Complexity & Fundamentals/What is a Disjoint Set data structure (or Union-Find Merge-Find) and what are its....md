---
title: "What is a Disjoint Set data structure (or Union-Find Merge-Find) and what are its..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is a Disjoint Set data structure (or Union-Find Merge-Find) and what are its..."
---

# 🎴 What is a Disjoint Set data structure (or Union-Find Merge-Find) and what are its...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is a Disjoint Set data structure (or Union-Find / Merge-Find) and what are its fundamental mathematical characteristics? #card

?
A **Disjoint Set** (also known as a _Union-Find set_ or _Merge-Find set_) stores a collection of disjoint subsets originating from a universal ground set $X = \{1, 2, \dots, n\}$.

Let $S = \{S_1, S_2, \dots, S_k\}$, with $1 \le k \le n$, be the collection of subsets. They must satisfy three fundamental properties:

1. **Inclusion**: $S_i \subseteq X, \quad \forall i = 1, \dots, k$
2. **Pairwise disjointness**: $S_i \cap S_j = \emptyset, \quad \forall i \neq j, \quad i,j = 1, \dots, k$
3. **Total union**: $\bigcup_{i=1}^{k} S_i = X$

Second diagram by Svjo - Own work, CC BY-SA 3.0, Link

⚠️ Warning:
The data structure **only allows **find** (Find) and **union** (Union) operations**.
It does not support in any way insertion or deletion operations of individual elements.
