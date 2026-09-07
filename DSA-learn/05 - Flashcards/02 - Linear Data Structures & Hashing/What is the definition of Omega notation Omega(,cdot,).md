---
title: "What is the definition of Omega notation Omega(,cdot,)"
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the definition of Omega notation Omega(,cdot,)"
---

# 🎴 What is the definition of Omega notation Omega(,cdot,)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the definition of "Omega" notation $\Omega(\,\cdot\,)$? #card

?
Given two functions $f,g : \mathbb{N} \to \mathbb{R}^+$, we say that:

```text
f(n) ∈ (g(n)) c > 0, \, n_0 ∈ {N} : [rgb]{0.047,0.565,0.933}{f(n) ≥q c g(n)} n ≥q n_0
```

**Intuition:** from a certain point onwards, $f(n)$ **_never lies below_** $c g(n)$ (_asymptotic \**lower \**bound_).

📝 Examples: $n^2 \in \Omega(n \log n), \quad 2^n \in \Omega(n^{100}), \quad n! \in \Omega(2^n)$
📌 Note:

$$
f(n) \in \Omega(g(n)) \iff g(n) \in O(f(n))
$$

                ⬆️ $\color{black}\Omega$ Expression
                Name




                $\color{black}\Omega(1)$
                (sublinear) constant


                $\color{black}\Omega(\log \log n)$
                (sublinear) $\color{black}\log \log$


                $\color{black}\Omega(\log n)$
                (sublinear) logarithmic


                $\color{black}\Omega(\sqrt[c]{n}), c > 1$
                sublinear


                $\color{black}\Omega(n)$
                linear


                $\color{black}\Omega(n \log n)$
                linearithmic


                $\color{black}\Omega(n^2)$
                quadratic


                $\color{black}\Omega(n^3)$
                cubic


                $\color{black}\Omega(n^k) (k \geq 1)$
                polynomial


                $\color{black}\Omega(a^n) (a > 1)$
                exponential


                $\color{black}\Omega(n!)$
                factorial




        perfect
        good
        acceptable
        unacceptable
