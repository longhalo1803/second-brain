---
title: "How does queue insertion enqueue(Q, x) work in a linked list implementation"
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
  - "How does queue insertion enqueue(Q, x) work in a linked list implementation"
---

# 🎴 How does queue insertion enqueue(Q, x) work in a linked list implementation

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How does queue insertion `enqueue(Q, x)` work in a linked list implementation? #card

?
The procedure `enqueue(Q, x)` allocates a new node and attaches it to the tail of the list.

**Pseudocode:**

```text
enqueue(Q, x)
    e := new_list_node()
    e.val := x
    e.next := NIL
    if Q.head = NIL then
        Q.head := e
    else
        Q.tail.next := e
    Q.tail := e
```

**Explanation:**

- If the queue was empty (`Q.head = NIL`), the new node becomes the head.
- If the queue was not empty, the new node is linked to the current last node: `Q.tail.next := e`.
- Finally, update `Q.tail := e`.
  **Computational cost:** $\Theta(1)$
