---
title: "What is a Rooted Tree and what are its fundamental properties"
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
  - "What is a Rooted Tree and what are its fundamental properties"
---

# 🎴 What is a Rooted Tree and what are its fundamental properties

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is a Rooted Tree and what are its fundamental properties? #card

?
A rooted tree $T=(V,E)$ is a pair of sets characterized by the following properties:

- $V$ is a set of **nodes** (or vertices).
- $E$ is a set of **directed edges** connecting pairs of nodes in $V$.
- One node in $V$ is the **root** $r$ of the tree.
- Every node in $V$, except for the root $r$, has **exactly one incoming edge**.

**Properties:**
• There exists a **unique directed path** from the root to every other node in the tree.
• **Absence of cycles:** There are NO circular paths within the tree.
