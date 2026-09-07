---
title: "📘 Exercise 16.1"
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
  - "📘 Exercise 16.1"
---

# 🎴 📘 Exercise 16.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 16.1

**Input:** A binary tree $T$ implemented with nodes and pointers (fields: $left$ pointing to right child, $right$ pointing to left child, $key$ storing node ID), and a pointer $p$ to a node in $T$.
**Output:** Print all IDs of the nodes that are ancestors of $p$ in $T$ followed by "no other ancestors", or print "no ancestors" if $p$ is the root.

Provide pseudocode of a recursive algorithm, analyze complexity, and show the sequence of calls/returns on an example of height at least 2. #card
?
**Reasoning:**
A node $u$ is an ancestor of $p$ if $p$ lies in its left or right subtree. Note the inverted naming given in the problem: `u.left` points to the right child and `u.right` points to the left child.

**Algorithm Description:**
If $p = T$, the root has no ancestors; print "no ancestors". Otherwise, invoke a recursive function that returns true if $p$ is found in the subtree rooted at $u$. If a child call returns true, the current node $u$ is an ancestor, so print $u.key$.

**Pseudocode:**

```text
Algorithm PrintAncestors(T, p):
    if T = NIL T = p then
        print "no ancestors"
    else
        PrintAncestorsRec(T, p)
        print "no other ancestors"

Function PrintAncestorsRec(u, p):
    if u = NIL then return FALSE
    if u = p then return TRUE
    if PrintAncestorsRec(u.left, p) PrintAncestorsRec(u.right, p) then
        print u.key
        return TRUE
    return FALSE
```

**Complexity:**
Visits each node at most once: $O(n)$ time, $O(h)$ auxiliary stack space.
