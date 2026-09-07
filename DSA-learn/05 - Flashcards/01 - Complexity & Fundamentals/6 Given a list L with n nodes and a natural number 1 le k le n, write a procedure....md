---
title: "6 Given a list L with n nodes and a natural number 1 le k le n, write a procedure..."
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
  - "6 Given a list L with n nodes and a natural number 1 le k le n, write a procedure..."
---

# 🎴 6 Given a list L with n nodes and a natural number 1 le k le n, write a procedure...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: 📝 6 Given a list $L$ with $n$ nodes and a natural number $1 \le k \le n$, write a procedure that prints the first node, deletes it, and then proceeds in a circular manner printing and deleting the node located after $k$ positions until the list is empty.

➡️ Example:
For $L = \langle 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13 \rangle$ and $k = 3$, the expected output is $\langle 1, 4, 7, 10, 13, 5, 9, 2, 8, 3, 12, 6, 11 \rangle$. #card
?

- If the list is not empty, print and delete the first element ($\textsf{L.val}$) using $\textsf{delete}(\textsf{L}, \textsf{L})$.
- Set a pointer $\textsf{p}$ to the first remaining node.
- While the list is not empty ($\textsf{p} \neq \textsf{NIL}$):
- Advance by $k-1$ positions. If during advancement the end of the list is reached ($\textsf{p} = \textsf{NIL}$), wrap around to the beginning ($\textsf{p} := \textsf{L}$).
- Print $\textsf{p.val}$ and delete the node with $\textsf{delete}(\textsf{L}, \textsf{p})$.
- Set $\textsf{p}$ to the next node (if $\textsf{p.next} \neq \textsf{NIL}$ then $\textsf{p} := \textsf{p.next}$, otherwise if it was the last node wrap around to $\textsf{p} := \textsf{L}$).
  **Pseudocode:**

```text
{aligned}                            // Skip(L, k)
    // if L ≠q NIL then
        // print L.val
        // delete(L, L)
        // p := L
        // while p ≠q NIL do
            // for i := 1 to k-1 do
                // p := p.next
                // if p = NIL then p := L
            // print p.val
            // delete(L, p)
            // if p.next ≠q NIL then
                // p := p.next
            // else
                // p := L
```
