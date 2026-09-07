---
title: "How does the procedure inserthead(L, e) work and what is its time complexity"
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
  - "How does the procedure inserthead(L, e) work and what is its time complexity"
---

# 🎴 How does the procedure inserthead(L, e) work and what is its time complexity

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: How does the procedure `insert_head(L, e)` work and what is its time complexity? #card

?
The procedure `insert_head(L, e)` inserts node `e` at the beginning of list `L`.

**Pseudocode:**

```text
insert_head(L, e)
    e.next := L
    L := e
```

**Steps:**

1. The `next` field of the new node `e` is set to point to the current head of the list (`L`).
2. The head pointer `L` is updated to point to node `e`.

**Computational cost:** $\Theta(1)$

📌 Note: the procedure works correctly even if the list `L` is empty (`L = NIL`).
