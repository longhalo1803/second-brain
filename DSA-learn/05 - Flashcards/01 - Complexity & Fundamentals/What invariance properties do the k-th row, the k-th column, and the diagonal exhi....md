---
title: "What invariance properties do the k-th row, the k-th column, and the diagonal exhi..."
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
  - "What invariance properties do the k-th row, the k-th column, and the diagonal exhi..."
---

# 🎴 What invariance properties do the k-th row, the k-th column, and the diagonal exhi...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What invariance properties do the k-th row, the $k$-th column, and the diagonal exhibit in matrix $D^{(k)}$? #card

?
During the update from matrix $D^{(k-1)}$ to matrix $D^{(k)}$, the following invariances hold:

      Component
      Property
      Analytical proof


      **$k$-th Row** ($i = k$)
      $\textsf{dist}(k, j, k) = \textsf{dist}(k, j, k-1)$
      $\min(\textsf{dist}(k,j,k-1),\ \underbrace{\textsf{dist}(k,k,k-1)}_{=0} + \textsf{dist}(k,j,k-1))$


      **$k$-th Column** ($j = k$)
      $\textsf{dist}(i, k, k) = \textsf{dist}(i, k, k-1)$
      $\min(\textsf{dist}(i,k,k-1),\ \textsf{dist}(i,k,k-1) + \underbrace{\textsf{dist}(k,k,k-1)}_{=0})$


      **Main Diagonal** ($i = j$)
      $\textsf{dist}(i, i, k) = 0$
      Remains identically zero in the absence of negative cycles.

💡 **Practical rule for manual calculation:** to compute matrix $D^{(k)}$, one can directly copy row $k$, column $k$, and the main diagonal from $D^{(k-1)}$ without having to perform comparisons.
