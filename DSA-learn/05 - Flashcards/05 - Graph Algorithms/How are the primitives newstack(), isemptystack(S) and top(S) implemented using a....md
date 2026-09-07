---
title: "How are the primitives newstack(), isemptystack(S) and top(S) implemented using a..."
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
  - "How are the primitives newstack(), isemptystack(S) and top(S) implemented using a..."
---

# 🎴 How are the primitives newstack(), isemptystack(S) and top(S) implemented using a...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How are the primitives `new_stack()`, `is_empty_stack(S)` and `top(S)` implemented using a list, and what are their costs? #card

?
**1. `new_stack()`:**

```text
new_stack()
    return new_list()
```

📌 $\small\color{gray}\begin{array}{ll}\textsf{new_list()} & \\\quad \texttt{return }\textsf{NIL} & \end{array}$
**
Cost:** $\Theta(1)$

**2. `is_empty_stack(S)`:**

```text
is_empty_stack(S)
    return (S = NIL)
```

**Cost:** $\Theta(1)$

**3. `top(S)`:**

```text
top(S)
    if NOT S = NIL then
        return S.val
    else
        return error
```

**Cost:** $\Theta(1)$
