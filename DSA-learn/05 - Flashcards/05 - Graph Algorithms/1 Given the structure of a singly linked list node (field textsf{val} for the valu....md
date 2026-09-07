---
title: "1 Given the structure of a singly linked list node (field textsf{val} for the valu..."
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
  - "1 Given the structure of a singly linked list node (field textsf{val} for the valu..."
---

# 🎴 1 Given the structure of a singly linked list node (field textsf{val} for the valu...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 1 Given the structure of a singly linked list node (field $\textsf{val}$ for the value and field $\textsf{next}$ for the pointer to the next node), describe and implement in pseudocode the fundamental list primitives. #card

?
The fundamental primitives for managing a singly linked list operate on nodes allocated via the function $\textsf{new_list_node}()$. The main primitives are:

**1. Creation of a new empty list ($\textsf{new_list}$):**

```text
{aligned}                            // new_list()
    // return NIL {aligned}
```

**2. Empty list check ($\textsf{is_empty_list}$):**

```text
{aligned}                            // is_empty_list(L)
    // return (L = NIL) {aligned}
```

**3. Insertion at the head (**$\textsf{insert_head}$**):** inserts node $\textsf{n}$ at the head of list $\textsf{L}$.

```text
{aligned}                            // insert_head(L, n)
    // n.next := L
    // return n {aligned}
```

**4. Deletion of a given node (**$\textsf{delete}$**):** disconnects from list $\textsf{L}$ the node pointed to by $\textsf{p}$.

```text
{aligned}                            // delete(L, p)
    // if L = p then
        // return L.next
    // tmp := L
    // while tmp.next ≠q NIL AND tmp.next ≠q p do
        // tmp := tmp.next
    // if tmp.next = p then
        // tmp.next := p.next
    // return L {aligned}
```

📌 Note: in this context we do not address garbage collection or memory deallocation. A disconnected node remains in memory and its fields are still accessible through a direct pointer.
