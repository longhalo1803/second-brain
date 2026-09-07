---
title: "7 Given a binary tree T storing integer values in the key field, write a recursive..."
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
  - "7 Given a binary tree T storing integer values in the key field, write a recursive..."
---

# 🎴 7 Given a binary tree T storing integer values in the key field, write a recursive...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 7 Given a binary tree $T$ storing integer values in the `key` field, write a recursive procedure that deletes from the tree all leaves that are **left children** and contain the **same integer** as their parent. #card

?
**Base case: **Empty tree (`t = NIL`): no action.
**Recursive case: **For the current node `t`, we check whether its left child `v = t.left` exists, is a leaf (`v.left = NIL` and `v.right = NIL`), and satisfies `v.key = t.key`. If so, we remove the leaf by setting `t.left := NIL`. We then proceed recursively on both subtrees.

**Pseudocode:**

```text
DeleteLeaves(t)
    if t ≠q NIL then
        v := t.left
        if v ≠q NIL AND v.left = NIL AND v.right = NIL AND v.key = t.key then
            t.left := NIL
        DeleteLeaves(t.left)
        DeleteLeaves(t.right)
```

Notice the following minor optimization: if the left child `v` is deleted (`t.left := NIL`), the algorithm still executes the call `DeleteLeaves(t.left)`, that is, `DeleteLeaves(NIL)`. The function handles this safely thanks to the `if t != NIL` check, but it is an unnecessary recursive call. It can be optimized using an `else` block:

```text
DeleteLeaves(t)
    if t ≠q NIL then
        v := t.left
        if v ≠q NIL AND v.left = NIL AND v.right = NIL AND v.key = t.key then
            t.left := NIL
        else
            DeleteLeaves(t.left)
        DeleteLeaves(t.right)
```

Main call: $\textsf{DeleteLeaves(T)}$.

📌 Note:
Without loss of generality, we assume boolean operators use _**short-circuit evaluation**_ (meaning an operand is evaluated only if the preceding one is not sufficient to determine the value of the expression) to avoid null pointer dereferencing.

In particular, for the $\texttt{AND}$ operator, if, for example, the first operand is `FALSE`, there is no need to evaluate the second, because the expression will be `FALSE` either way. Similarly, for the $\texttt{OR}$ operator, if the first operand is `TRUE`, the second does not need to be evaluated because the expression will be `TRUE` regardless.

In this case, the condition $\textsf{(v ≠ NIL }\texttt{AND}\textsf{ v.left = NIL }\texttt{AND}\textsf{ v.right = NIL }\texttt{AND}\textsf{ v.key = t.key)}$ will not cause an error if $\textsf{v = NIL}$ because evaluation stops after the first $\texttt{AND}$. Otherwise, if $\textsf{v = NIL}$, evaluating $\textsf{v.left = NIL}$ would return an error, as it is impossible to access the $\textsf{left}$ field of a null pointer.

📌 Alternative:

```text
DeleteLeaves(t, parentVal)
    if t = NIL then
        return NIL
        if t.left = NIL AND t.right = NIL AND t.key = parentVal then // If it is a valid leaf, delete it
        return NIL
        t.left := DeleteLeaves(t.left, t.key) // Pass its own value to the left child
        t.right := DeleteLeaves(t.right, NIL) // Pass NIL to the right child
    return t
```
