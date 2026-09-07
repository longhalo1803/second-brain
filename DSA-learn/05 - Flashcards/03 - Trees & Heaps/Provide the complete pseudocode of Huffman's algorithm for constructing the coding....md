---
title: "Provide the complete pseudocode of Huffman's algorithm for constructing the coding..."
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
  - "Provide the complete pseudocode of Huffman's algorithm for constructing the coding..."
---

# 🎴 Provide the complete pseudocode of Huffman's algorithm for constructing the coding...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 Provide the complete pseudocode of Huffman's algorithm for constructing the coding tree. #card

?
**Input:**

$\textcolor{#00a2e8}{\Sigma[1..|\Sigma|]}$ → array of alphabet characters

$\textcolor{#f58220}{f[1..|\Sigma|]}$ → character frequencies in the text

Tree nodes (`tree_node`) contain the fields:

`c` ( character $\textcolor{#00a2e8}{\in \Sigma \cup \{'-\}'}$ ),

`fr` ( sum of character frequencies in the subtree ),

`left` and `right` (pointers to left and right children).

```text
Huffman({#00a2e8}{[1..||]}, {#f58220}{f[1..||]}, {#00a2e8}{||})
    ≤ft. {#00a800}{Q := new_priority_queue()}
    for i := 1 to {#00a2e8}{||} do
        t := new_tree_node()
        t.c := {#00a2e8}{[i]}
        t.fr := {#f58220}{f[i]}
        t.left := NIL
        t.right := NIL
        {#00a800}{enQueue(Q, t, }{#f58220}{f[i]}{#00a800}{)} } Leaf initialization and insertion into Q
        for i := 1 to {#00a2e8}{||} - 1 do // ||-1 merge iterations
        ≤ft. t1 := {#00a800}{DeQueue(Q)}
        t2 := {#00a800}{DeQueue(Q)} } Extraction of the 2 minimums
        ≤ft. t := new_tree_node()
        t.c := {#00a2e8}{'-'}
        t.fr := {#f58220}{t1.fr + t2.fr}
        t.left := t1
        t.right := t2
        {#00a800}{enQueue(Q, t, }{#f58220}{t1.fr + t2.fr}{#00a800}{)} } Internal node and reinsertion (Greedy Choice)
        return {#00a800}{DeQueue(Q)} // Return the root of the tree
```
