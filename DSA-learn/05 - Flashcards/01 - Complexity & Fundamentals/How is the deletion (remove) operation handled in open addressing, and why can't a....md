---
title: "How is the deletion (remove) operation handled in open addressing, and why can't a..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "How is the deletion (remove) operation handled in open addressing, and why can't a..."
---

# 🎴 How is the deletion (remove) operation handled in open addressing, and why can't a...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: How is the **deletion (remove)** operation handled in open addressing, and why can't a slot simply be set to empty (`NIL`)? #card

?
One cannot simply delete an element by setting its cell to empty (`NIL`).

**Reason:**
The search for a key terminates when it encounters an empty slot, interpreting it as evidence that the desired key was never inserted. If an intermediate slot belonging to the probe sequence of other keys were cleared, subsequent searches for those keys **would terminate prematurely**, yielding a false negative.

**Solution (special `DELETED` marker):**

- The cell is marked with a special sentinel value (e.g., `DELETED` or `DEL`).
- During **search**: the algorithm does not stop on `DELETED`, but continues along the probe sequence.
- During **insertion**: a slot with value `DELETED` can be considered free and reused to store a new key.
