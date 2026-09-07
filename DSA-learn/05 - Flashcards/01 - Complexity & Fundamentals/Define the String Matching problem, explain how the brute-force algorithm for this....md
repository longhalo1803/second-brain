---
title: "Define the String Matching problem, explain how the brute-force algorithm for this..."
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
  - "Define the String Matching problem, explain how the brute-force algorithm for this..."
---

# 🎴 Define the String Matching problem, explain how the brute-force algorithm for this...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: ❓\* Define the String Matching problem, explain how the brute-force algorithm for this problem works, and discuss its computational cost. #card

?

- **Problem Definition:**  
  Given a text $T[0 \dots n-1]$ of length $n$ and a pattern (or template) $P[0 \dots m-1]$ of length $m$ (with $m \le n$), both composed of characters from a finite alphabet $\Sigma$, the String Matching problem consists of finding all occurrences of $P$ in $T$, which means finding all valid shifts $s \in \{0, 1, \dots, n-m\}$ such that:

$$
T[s \dots s+m-1] = P[0 \dots m-1]
$$

that is, $T[s+j] = P[j]$ for each $j \in \{0, \dots, m-1\}$.

- **Brute-Force Algorithm Operation:**  
  The algorithm systematically checks every possible alignment (shift) of $P$ against $T$:
- Iterate with an index $s$ ranging from $0$ to $n - m$.
- For each fixed value of $s$, perform a character-by-character comparison between $P[j]$ and $T[s+j]$ for $j$ from $0$ to $m-1$.
- If a difference is detected during comparison ($T[s+j] \ne P[j]$), the inner loop terminates immediately (mismatch), $s$ is incremented by $1$, and matching restarts from the beginning of the pattern.
- If the inner loop successfully compares all $m$ characters without error, the algorithm reports that an occurrence has been found at shift $s$.
- **Computational Cost:**
- **Worst Case:** $\mathcal{O}((n - m + 1) \cdot m)$. This occurs when for each position $s$, almost all characters are compared before finding a mismatch or discovering a match (e.g., $T = \text{"AAAAAAAAAA"}$ and $P = \text{"AAAB"}$).
- **Best Case:** $\mathcal{O}(n)$, when an immediate mismatch is found on the very first character of every shift ($T[s] \ne P[0]$).
- Auxiliary space is $\mathcal{O}(1)$.
