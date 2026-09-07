---
title: "How is insertion at an arbitrary position insertpos(L, e, i) implemented using the..."
tags:
  - dsa
  - flashcards
  - clrs
  - graphs
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "How is insertion at an arbitrary position insertpos(L, e, i) implemented using the..."
---

# 🎴 How is insertion at an arbitrary position insertpos(L, e, i) implemented using the...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How is insertion at an arbitrary position `insert_pos(L, e, i)` implemented using the other list primitives? #card

?
The procedure `insert_pos(L, e, i)` inserts the node `e` at position `i` of the list `L`.

**Pseudocode:**

```text
insert_pos(L, e, i)
    if i = 0 then
        insert_head(L, e)
    else
        p := search(L, i - 1)
        if NOT (p = NIL) then
            insert_next(p, e)
```

**Explanation:**

- If $i = 0$, insertion is performed directly at the head using `insert_head`.
- Otherwise, search for the node at position $i - 1$ via `search(L, i-1)` and, if it exists, insert `e` immediately after it using `insert_next`.
  **Computational cost:** $\Theta(i)$ (dominated by the call to `search`).
