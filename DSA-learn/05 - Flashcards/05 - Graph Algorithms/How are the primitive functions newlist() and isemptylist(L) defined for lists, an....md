---
title: "How are the primitive functions newlist() and isemptylist(L) defined for lists, an..."
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
  - "How are the primitive functions newlist() and isemptylist(L) defined for lists, an..."
---

# 🎴 How are the primitive functions newlist() and isemptylist(L) defined for lists, an...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How are the primitive functions `new_list()` and `is_empty_list(L)` defined for lists, and what is their complexity? #card

?
**1. `new_list()`**:
Creates a new empty list by returning the `NIL` pointer.

```text
new_list()
    return NIL
```

**Computational cost:** $\Theta(1)$

**2. `is_empty_list(L)`**:
Checks whether the list `L` is empty (i.e., whether the head points to `NIL`).

```text
is_empty_list(L)
    return L = NIL
```

**Computational cost:** $\Theta(1)$
