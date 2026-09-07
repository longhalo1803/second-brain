---
title: "How does removal from the head of the queue dequeue(Q) work on a linked list"
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
  - "How does removal from the head of the queue dequeue(Q) work on a linked list"
---

# 🎴 How does removal from the head of the queue dequeue(Q) work on a linked list

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How does removal from the head of the queue `dequeue(Q)` work on a linked list? #card

?
The function `dequeue(Q)` extracts and removes the element at the head of the queue.

**Pseudocode:**

```text
dequeue(Q)
    if NOT is_empty_queue(Q) then
        x := first(Q)
        Q.head := Q.head.next
        if Q.head = NIL then
            Q.tail := NIL
        return x
    else
        return error
```

**Explanation:**

- Retrieve the head value: `x := first(Q)`.
- Advance the head pointer: `Q.head := Q.head.next`.
- **Edge case:** if the queue becomes empty after extraction (`Q.head = NIL`), `Q.tail` must also be reset to `NIL`.
  **Computational cost:** $\Theta(1)$
