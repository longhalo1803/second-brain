---
title: "How are the primitives newqueue(), isemptyqueue(Q), and first(Q) implemented on a..."
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
  - "How are the primitives newqueue(), isemptyqueue(Q), and first(Q) implemented on a..."
---

# 🎴 How are the primitives newqueue(), isemptyqueue(Q), and first(Q) implemented on a...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How are the primitives `new_queue()`, `is_empty_queue(Q)`, and `first(Q)` implemented on a linked list? #card

?
**1. `new_queue()`:**

```text
new_queue()
    Q := new_queue_node()
    Q.head := NIL
    Q.tail := NIL
    return Q
```

**Cost:** $\Theta(1)$

**2. `is_empty_queue(Q)`:**

```text
is_empty_queue(Q)
    return (Q.head = NIL)
```

**Cost:** $\Theta(1)$

**3. `first(Q)`:**

```text
first(Q)
    if Q.head ≠q NIL then
        return Q.head.val
    else
        return error
```

**Cost:** $\Theta(1)$
