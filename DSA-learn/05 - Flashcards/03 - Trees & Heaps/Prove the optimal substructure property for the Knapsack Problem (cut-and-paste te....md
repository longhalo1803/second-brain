---
title: "Prove the optimal substructure property for the Knapsack Problem (cut-and-paste te..."
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
  - "Prove the optimal substructure property for the Knapsack Problem (cut-and-paste te..."
---

# 🎴 Prove the optimal substructure property for the Knapsack Problem (cut-and-paste te...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Prove the optimal substructure property for the Knapsack Problem (_cut-and-paste_ technique). #card

?
**Statement:**
If a selection of items forms an optimal filling for a knapsack of capacity $W$, then the sub-selection contained in any portion of the knapsack of capacity $w \le W$ must be an optimal filling for that capacity $w$.

**Proof by contradiction (Cut-and-Paste):**

- Let $S$ be the optimal solution for the knapsack of capacity $W$, and let $S_w \subseteq S$ be the sub-solution occupying a remaining capacity/portion $w \le W$.
- Suppose for the sake of contradiction that $S_w$ is not optimal for capacity $w$, meaning there exists another selection $S'_w$ with weight $\le w$ having strictly greater value: $\text{val}(S'_w) > \text{val}(S_w)$.
- By replacing (cut-and-paste) $S_w$ with $S'_w$ inside $S$, we would obtain a new feasible solution $S' = (S \setminus S_w) \cup S'_w$ with total weight $\le W$.
- The total value would be:

$$

\text{val}(S') = \text{val}(S) - \text{val}(S_w) + \text{val}(S'\_w) > \text{val}(S)

$$

- This contradicts the initial assumption that $S$ was an optimal solution for $W$.

Quindi, la porzione di capacità $w$ deve necessariamente contenere una soluzione ottima locale.
