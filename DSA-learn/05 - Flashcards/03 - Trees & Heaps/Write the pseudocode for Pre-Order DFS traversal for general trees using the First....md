---
title: "Write the pseudocode for Pre-Order DFS traversal for general trees using the First..."
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
  - "Write the pseudocode for Pre-Order DFS traversal for general trees using the First..."
---

# 🎴 Write the pseudocode for Pre-Order DFS traversal for general trees using the First...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝🟢 Write the pseudocode for Pre-Order DFS traversal for general trees **using the FirstChild-NextSibling representation**. #card

?
The current node $t$ is processed, then the pointer to its first child ($w = t.\textsf{firstchild}$) is retrieved, and all siblings are iterated over by making recursive traversal calls as long as $w \neq \textsf{NIL}$.

**Pseudocode:**

```text
DFS_pre_order(t)
    if NOT (t = NIL) then
                {#fa1105}print t.val {#fa1105}{// process t}
        w := t.firstchild
        while NOT (w = NIL) do
            DFS_pre_order(w)
            w := w.nextsibling
```

Main call: $\textsf{DFS_pre_order(T)}$
