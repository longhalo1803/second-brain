---
title: "What is the algorithm for decoding a compressed file using a prefix coding tree"
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
  - "What is the algorithm for decoding a compressed file using a prefix coding tree"
---

# 🎴 What is the algorithm for decoding a compressed file using a prefix coding tree

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 What is the algorithm for decoding a compressed file using a prefix coding tree? #card

?
The algorithm iterates through the bits of the compressed file from start to end, moving through the tree starting from the root:

**Procedure:**

- Start at the root of the coding tree.

- While the file has not ended, read the current bit:

- If the bit is 0, traverse to the left child.

- If the bit is 1, traverse to the right child.

- If you reach a leaf:

- Print (output) the character stored in the leaf.

- Immediately return to the root to decode the next character.

```text
Decode(T, CompressedFile)
    node := T.root
    while NOT end_of_file(CompressedFile) do
        bit := read_bit(CompressedFile)
        if bit = 0 then
            node := node.left
        else
            node := node.right
        if is_leaf(node) then
            print(node.c)
            node := T.root
```

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
