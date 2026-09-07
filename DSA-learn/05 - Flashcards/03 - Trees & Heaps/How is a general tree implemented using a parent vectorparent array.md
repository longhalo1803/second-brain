---
title: "How is a general tree implemented using a parent vectorparent array"
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
  - "How is a general tree implemented using a parent vectorparent array"
---

# 🎴 How is a general tree implemented using a parent vectorparent array

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is a general tree implemented using a _**parent vector**_/parent array? #card

?
Assuming nodes have integer identifiers in the range $[1 .. n]$, the entire tree is represented via an array of pairs:

$$

(val, p)

$$

where `val` is the value stored in the node and `p` is the array index of the parent node.

**Characteristics:**
• The root has $0$ (or `NIL`) as its parent indicator.
• It is an upward-oriented structure: it allows navigating quickly from any node up to the root.

📝 Example:
Tree with root $A$ at id 1, with children $B$ (id 2) and $C$ (id 3):
Array = `[1: (A, 0), 2: (B, 1), 3: (C, 1)]`.

      1
      2
      3
      4
      5
      6
      7
      8
      9
      10
      11




      (A,0)
      (B,1)
      (C,1)
      (D,2)
      (E,2)
      (G,3)
      (F,3)
      (L,5)
      (M,6)
      (I,4)
      (H,4)
