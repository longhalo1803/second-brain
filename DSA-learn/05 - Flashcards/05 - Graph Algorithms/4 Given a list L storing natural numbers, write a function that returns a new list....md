---
title: "4 Given a list L storing natural numbers, write a function that returns a new list..."
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
  - "4 Given a list L storing natural numbers, write a function that returns a new list..."
---

# 🎴 4 Given a list L storing natural numbers, write a function that returns a new list...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 4 Given a list $L$ storing natural numbers, write a function that returns a new list containing **only the even values** present in $L$. Consider both the basic solution and the variant in which the original order must be preserved. #card

?
**1. Basic solution (with insertion at the head):**
Create a new empty list $R$. Traversing $L$, for each node whose value is even, allocate a new node and insert it at the head of $R$ using the $\textsf{insert_head}$ primitive.

```text
{aligned}                            // EvenList(L)
    // R := new_list()
    // while L ≠q NIL do
        // if (L.val 2 = 0) then
            // n := new_list_node()
            // n.val := L.val
            // insert_head(R, n)
        // L := L.next
    // return R {aligned}
```

📌 Note: insertion at the head reverses the order of the even values compared to the original list.

**2. Variant: preserving the original order (recursive solution):**
To preserve the original order without reversing the list, we can use a recursive approach:

```text
{aligned}                            // EvenListPreserveOrder(L)
    // if L = NIL then
        // return NIL
    // if (L.val 2 = 0) then
        // n := new_list_node()
        // n.val := L.val
        // n.next := EvenListPreserveOrder(L.next)
        // return n
    // else
        // return EvenListPreserveOrder(L.next) {aligned}
```

📌 Note: both algorithms have a computational cost of $\Theta(n)$.
