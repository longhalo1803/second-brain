---
title: "What is the growth rate order among common functions"
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
  - "What is the growth rate order among common functions"
---

# 🎴 What is the growth rate order among common functions

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the growth rate order among common functions? #card

?
As with the logarithm, it can be shown that these orders of growth hold, from smallest to largest:

$$
\log n \prec n \prec n \log n \prec n^2 \prec 2^n \prec n!
$$

Each of these functions belongs to the Big-$O$ order of the subsequent ones (up to a multiplicative constant), meaning it grows asymptotically slower or equal.

        ⬇️ $\color{black}O$ Expression
        Name




        $\color{black}O(1)$
        (sublinear) constant


        $\color{black}O(\log \log n)$
        (sublinear) $\color{black}\log \log$


        $\color{black}O(\log n)$
        (sublinear) logarithmic


        $\color{black}O(\sqrt[c]{n}), \; c > 1$
        sublinear


        $\color{black}O(n)$
        linear


        $\color{black}O(n \log n)$
        linearithmic


        $\color{black}O(n^2)$
        quadratic


        $\color{black}O(n^3)$
        cubic


        $\color{black}O(n^k), \;k \geq 1$
        polynomial


        $\color{black}O(a^n),\; a > 1$
        exponential


        $\color{black}O(n!)$
        factorial




    perfect
    good
    acceptable
    unacceptable

Code examples: https://www.hello-algo.com/en/chapter_computational_complexity/time_complexity/#234-common-types
