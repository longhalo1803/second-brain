---
title: "What is the underlying idea of Counting Sort (basic non-stable version)"
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the underlying idea of Counting Sort (basic non-stable version)"
---

# 🎴 What is the underlying idea of Counting Sort (basic non-stable version)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the underlying idea of Counting Sort (basic / non-stable version)? #card

?
The idea develops in two main phases:

- **Counting occurrences:** for each possible value $j \in [0, k]$, count how many elements in $A$ are equal to $j$, recording the frequencies in an auxiliary array $C$ of size $k+1$.
- **Regenerating $A$:** iterate through array $C$ from index $0$ to index $k$, overwriting sequence $A$ with each value $j$ a number of times equal to $C[j]$.
  📌 Note: the auxiliary array $C$ has size $k+1$ because indices range from $0$ to $k$.

📝 Example:
If $A = \langle 5, 8, 3, 0, 8, 10, 7, 7, 3, 2 \rangle$ with $k=10$, the value $3$ appears 2 times, so $C[3] = 2$.
During regeneration, the value $3$ is written 2 times consecutively into $A$.

https://visualgo.net/en/sorting?mode=Counting (click Sort on bottom left)
