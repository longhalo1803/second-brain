---
title: "6 Given a general tree T implemented with firstChild and nextSibling pointers. Wri..."
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
  - "6 Given a general tree T implemented with firstChild and nextSibling pointers. Wri..."
---

# 🎴 6 Given a general tree T implemented with firstChild and nextSibling pointers. Wri...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 6 Given a general tree $T$ implemented with `firstChild` and `nextSibling` pointers. Write a recursive function based on DFS traversal to compute the total number of nodes in the tree. #card

?
If the tree is empty the answer is $0$. Otherwise, the number of nodes is equal to $1$ (the root itself) plus the sum of nodes in all subtrees rooted at its children (traversed sequentially via `firstChild` and `nextSibling`).

**1. Pseudocode (recursive version, but iterative over siblings):**

```text
CountNodes_DFS(t)
    if t = NIL then return 0
    count := 1
    v := t.firstChild
    while v ≠q NIL do
        count := count + CountNodes_DFS(v)
        v := v.nextSibling
    return count
```

(_Note: the counter `count` does not get reset because each recursive call has its own local count variable on its memory stack (call frame), and the results are summed together as the functions return. If `count` had been a global variable, the assignment count := 1 would have indeed overwritten the count at each call._)

**2. Purely recursive version:**
Exploits the binary tree representation by delegating entirely to the recursion stack both the descent down children and the iteration over siblings.

```text
CountNodes_DFS(t)
    if t = NIL then return 0
    return 1 + CountNodes_DFS(t.firstChild) + CountNodes_DFS(t.nextSibling)
```

**3. Overly verbose version (with explicit case checks) ❌**Redundantly handles each combination of presence/absence of `firstChild` and `nextSibling` pointers.

```text
CountNodes_DFS(t)
    if t = NIL then return 0
    if t.firstChild ≠q NIL AND t.nextSibling ≠q NIL then
        return 1 + CountNodes_DFS(t.firstChild) + CountNodes_DFS(t.nextSibling)
    else if t.firstChild = NIL AND t.nextSibling ≠q NIL then
        return 1 + CountNodes_DFS(t.nextSibling)
    else if t.firstChild ≠q NIL AND t.nextSibling = NIL then
        return 1 + CountNodes_DFS(t.firstChild)
    else
        return 1
```

**Computational cost: **$\Theta(n)$, since each node of the tree is visited exactly once.
