---
title: "Exercise 12"
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
  - "Exercise 12"
---

# 🎴 Exercise 12

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Exercise 12

Write a recursive procedure that, given as input two nodes $s, v \in V$ of a graph $G = (V, E)$ and the array $\textsf{prev}[]$ computed by a BFS with source at $s$, prints the path (node by node) leading from $s$ to $v$ in $G$. #card
?
The array $\textsf{prev}[]$ stores, for each node, the node's parent in the BFS tree.
To print the path from source $s$ to node $v$ we use recursion:
• **Base case:** if node $v$ is indeed source $s$, we print $s$;
• **Non-base case:** if $v \neq s$, we first print the path from $s$ to the parent of $v$ via recursive call, and AFTERWARDS (upon returning from the call) we print $v$. We add a check to verify that the path exists ($\textsf{prev}[v] \neq \textsf{NIL}$). The check is performed on the parent of $v$, which must exist and be different from NIL.

```text
PrintPath(prev[], s, v)
    if s = v then
        print s
    else
        if prev[v] = NIL then
            print "no path exists"
        else
            PrintPath(prev[], s, prev[v])
            print v
```
