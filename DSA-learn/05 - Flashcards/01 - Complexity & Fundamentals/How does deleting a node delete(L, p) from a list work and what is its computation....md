---
title: "How does deleting a node delete(L, p) from a list work and what is its computation..."
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
  - "How does deleting a node delete(L, p) from a list work and what is its computation..."
---

# 🎴 How does deleting a node delete(L, p) from a list work and what is its computation...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: How does deleting a node `delete(L, p)` from a list work and what is its computational cost? #card

?
The procedure `delete(L, p)` removes from list `L` the node pointed to by `p`. If `p` does not belong to the list, the list remains unchanged.

**Pseudocode:**

```text
delete(L, p)
    if p = L then
        L := L.next
    else
        tmp := L
        while ( tmp ≠q NIL AND tmp.next ≠q p ) do
            tmp := tmp.next
        if tmp ≠q NIL then
            tmp.next := p.next
```

📌 Note: this version uses pass-by-reference, meaning it directly modifies L (the order of operations in the while loop is important, in particular you must ensure that `tmp` is not null _before_ accessing `tmp.next`!)

**Explanation:**

- If `p` is the head (`p = L`), simply advance the head: `L := L.next`.
- Otherwise, traverse the list to find the node preceding `p` (i.e., such that `tmp.next = p`), and bypass `p` by setting `tmp.next := p.next`.
  **Computational cost:** $\Theta(n)$ in the worst case (since it requires searching for the preceding node).

📌 Alternative version:
This equivalent "functional" style version does not modify the caller's `L` variable, but works on the passed copy and returns the new pointer to the head, which the caller must reassign with `L := delete(L, p)`).

```text
delete(L, p)
    if L = p then
        return L.next
    tmp := L
    while ( tmp.next ≠q NIL AND tmp.next ≠q p ) do
        tmp := tmp.next
    if tmp.next = p then
        tmp.next := p.next
    return L
```
