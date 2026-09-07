---
title: "What is the optimal choice of constant A in the Multiplication Method proposed by..."
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
  - "What is the optimal choice of constant A in the Multiplication Method proposed by..."
---

# 🎴 What is the optimal choice of constant A in the Multiplication Method proposed by...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is the optimal choice of constant $A$ in the **Multiplication Method** proposed by Knuth? #card

?
According to studies by Donald Knuth, a particularly effective choice for constant $A$ is related to the golden ratio:

$$
A = \frac{\sqrt{5} - 1}{2} \approx 0.6180339887\dots
$$

**Rationale:** this value distributes the fractional parts $A \cdot k \bmod 1$ remarkably uniformly, avoiding anomalous clustering even when keys contain strong arithmetic regularities or consecutive sequences.
