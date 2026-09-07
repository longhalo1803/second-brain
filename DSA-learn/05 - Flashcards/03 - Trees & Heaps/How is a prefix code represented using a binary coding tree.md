---
title: "How is a prefix code represented using a binary coding tree"
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
  - "How is a prefix code represented using a binary coding tree"
---

# 🎴 How is a prefix code represented using a binary coding tree

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is a prefix code represented using a binary coding tree? #card

?
A prefix code is represented as a **binary coding tree**:

• **Edges** labeled with `0` (to the left child) and `1` (to the right child).
• **Characters** of the alphabet placed **exclusively at the leaves** of the tree.
• Root-to-leaf path = character encoding

📌 Note:
Since characters are located only at the leaves, no path to a character can be a prefix of the path to another character.

        a
        b
        c
        d
        e
        f




        0
        100
        101
        111
        1100
        1101
