---
title: "Write the pseudocode for Post-Order DFS traversal for general trees using the Firs..."
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
  - "Write the pseudocode for Post-Order DFS traversal for general trees using the Firs..."
---

# 🎴 Write the pseudocode for Post-Order DFS traversal for general trees using the Firs...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝🟢 Write the pseudocode for Post-Order DFS traversal for general trees **using the FirstChild-NextSibling representation**. #card

?
The chain of children starting from `firstchild` is traversed first by executing recursive calls on each of them, and only after completing the exploration of all children is node $t$ processed and printed.

**Pseudocode:**

```text
DFS_post_order(t)
    if NOT (t = NIL) then
        w := t.firstchild
        while NOT (w = NIL) do
            DFS_post_order(w)
            w := w.nextsibling
                {#fa1105}print t.val {#fa1105}{// process t}
```

Main call: $\textsf{DFS_post_order(T)}$
