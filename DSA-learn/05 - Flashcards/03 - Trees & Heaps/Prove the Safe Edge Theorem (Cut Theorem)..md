---
title: "Prove the Safe Edge Theorem (Cut Theorem)."
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
  - "Prove the Safe Edge Theorem (Cut Theorem)."
---

# 🎴 Prove the Safe Edge Theorem (Cut Theorem).

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Prove the Safe Edge Theorem (Cut Theorem). #card

?
Let $e = (u,v)$ be a minimum-cost edge crossing the cut $(S, V \setminus S)$ and let $T$ be an arbitrary MST for $G$.

Two cases arise:

- **Case 1: $e \in T$.** The edge already belongs to the MST $T$, the claim is immediately verified.
- **Case 2: $e \notin T$.**
- Since $T$ is a spanning tree for all vertices $V$, there must exist a path in $T$ connecting $u \in S$ to $v \in V \setminus S$.
- This path must necessarily cross the cut $(S, V \setminus S)$ via at least one other edge $e' = (u', v') \in T$ with $u' \in S$ and $v' \in V \setminus S$.
- Since $e$ is a minimum-cost edge crossing the cut, it holds that:

$$

c(e) \leq c(e')

$$

- Adding edge $e$ to $T$ creates a unique cycle containing both $e$ and $e'$. If we remove edge $e'$, we obtain a new spanning tree:

$$

T' = (T \setminus \{e'\}) \cup \{e\}

$$

- The cost of the new tree $T'$ is:

$$

\text{cost}(T') = \text{cost}(T) - c(e') + c(e)

$$

- Since $c(e) \leq c(e')$, we have $\text{cost}(T') \leq \text{cost}(T)$.
- However, since $T$ is an MST, its cost is the absolute minimum $\implies$ it cannot be that $\text{cost}(T') < \text{cost}(T)$. It follows that $\text{cost}(T') = \text{cost}(T)$ must hold and therefore $c(e) = c(e')$.Thus, $T'$ is also an MST for $G$ and contains edge $e$. $\blacksquare$
