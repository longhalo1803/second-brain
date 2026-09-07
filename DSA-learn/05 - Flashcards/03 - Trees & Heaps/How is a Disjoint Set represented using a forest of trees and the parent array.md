---
title: "How is a Disjoint Set represented using a forest of trees and the parent array"
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
  - "How is a Disjoint Set represented using a forest of trees and the parent array"
---

# 🎴 How is a Disjoint Set represented using a forest of trees and the parent array

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is a Disjoint Set represented using a forest of trees and the parent array? #card

?
In the concrete implementation using a **forest of trees**:
• **Each set** is represented by a directed tree.
• **Each set has a representative**, which coincides with the **root** of the tree.
• The forest is stored via the **parent array** (denoted by `DS` or `p`) of size $n$. For each node $i$, `DS[i]` contains the index of its parent; for the root $r$, the convention `DS[r] = r` (self-loop) holds.

📝 Example:
In the diagram above, `Find-set(DS, 7) == 5` following the path to the root $7 \to 1 \to 5$.
In the parent array, we have: `DS[7]=1`, `DS[1]=5`, `DS[5]=5`.
