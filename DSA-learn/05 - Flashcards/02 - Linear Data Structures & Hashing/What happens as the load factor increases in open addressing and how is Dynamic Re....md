---
title: "What happens as the load factor increases in open addressing and how is Dynamic Re..."
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What happens as the load factor increases in open addressing and how is Dynamic Re..."
---

# 🎴 What happens as the load factor increases in open addressing and how is Dynamic Re...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What happens as the load factor increases in open addressing and how is **Dynamic Rehashing** applied? #card

?
In open addressing, the load factor must satisfy $0 \le \alpha \le 1$. If the table fills up completely, no further insertions are possible and the structure suffers an **overflow**.

**How to prevent degradation and overflow:**
When the load factor exceeds a certain critical threshold (typically between $0.5$ and $0.75$):

- Allocate a new array with doubled size: $2m$.
- Recompute positions (re-hashing) and insert all keys into the new table.**Effects of rehashing:**
- The load factor $\alpha$ is cut in half.
- Cells marked `DELETED` that were slowing down searches are completely eliminated.
- Cost of the operation: $O(n) = O(m)$ in the worst case for resizing, but with an **amortized $O(1)$** cost per single operation.
