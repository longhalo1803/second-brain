---
title: "How are the primitives push(S, x) and pop(S) implemented using a linked list"
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
  - "How are the primitives push(S, x) and pop(S) implemented using a linked list"
---

# 🎴 How are the primitives push(S, x) and pop(S) implemented using a linked list

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How are the primitives `push(S, x)` and `pop(S)` implemented using a linked list? #card

?
**1. `push(S, x)`** (Procedure with pass-by-reference):

```text
push(S, x)
    e := new_list_node()
    e.val := x
    e.next := S
    S := e
```

**Cost:** $\Theta(1)$

**2. `pop(S)`** (function with pass-by-reference = direct modification of S, not a copy of it):

```text
pop(S)
    if NOT S = NIL then
        x := top(S)
        S := S.next
        return x
    else
        return error
```

**Cost:** $\Theta(1)$
