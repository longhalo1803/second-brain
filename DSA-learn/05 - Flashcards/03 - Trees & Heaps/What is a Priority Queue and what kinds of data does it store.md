---
title: "What is a Priority Queue and what kinds of data does it store"
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
  - "What is a Priority Queue and what kinds of data does it store"
---

# 🎴 What is a Priority Queue and what kinds of data does it store

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is a Priority Queue and what kinds of data does it store? #card

?
A **Priority Queue** is an abstract data type that stores a **collection of pairs**:

```text
(el, pr)
```

where `el` is the element/object and `pr` is its priority (a value belonging to a totally ordered set).

The **highest priority** can correspond to the minimum value or the maximum value of `pr` depending on the problem's requirements:
**• Min-Priority Queue**: the minimum value of `pr` has the highest priority.
**• Max-Priority Queue**: the maximum value of `pr` has the highest priority.

📝 Real-world examples:

- _Queue (exam, date)_: highest priority given to the exam with the closest (minimum) date.
- _Queue (task, wage)_: highest priority given to the task with the highest (maximum) compensation.
