---
title: "What is the fundamental proposition regarding rank, and what inequality derives fr..."
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
  - "What is the fundamental proposition regarding rank, and what inequality derives fr..."
---

# 🎴 What is the fundamental proposition regarding rank, and what inequality derives fr...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the fundamental proposition regarding rank, and what inequality derives from it? #card

?
**PROPOSITION (Rank Heuristic)**:
Using the rank heuristic, a tree in the forest rooted at $r$ has **at least $2^{\textsf{rank}[r]}$ nodes**.

**Corollary / Algebraic consequence**:
If a tree rooted at $r$ contains a total of $k$ nodes (with $k \le n$), by the proposition above we have:

```text
k ≥ 2^{rank[r]} _2 k ≥ rank[r] rank[r] ≤ _2 k ≤ _2 n
```

📌 Note:
This fundamental property guarantees that the height of any tree in the forest grows at most logarithmically with respect to the number of elements.
