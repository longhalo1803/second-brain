---
title: "What are the algebraic propertiesrules of Big-O notation"
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
  - "What are the algebraic propertiesrules of Big-O notation"
---

# 🎴 What are the algebraic propertiesrules of Big-O notation

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What are the algebraic properties/rules of Big-O notation? #card

?

- **Multiplication**: if $f(n) \in O(g(n)) \implies a \cdot f(n) \in O(g(n))$.
  📝 Ex.: $\log n \in O(n) \implies 7 \log n \in O(n)$

- **Sum**: $d(n) \in O(f(n)), e(n) \in O(g(n)) \implies d(n)+e(n) \in O(\max\{f,g\})$.
  📝 Ex.: $\log n \in O(n), \sqrt{n} \in O(n) \implies \log n + \sqrt{n} \in O(n) \quad (\sqrt{n} = n^{1/2} > \log n)$

- **Product**: $d(n) \in O(f(n)), e(n) \in O(g(n)) \implies d(n)\cdot e(n) \in O(f\cdot g)$.
  📝 Ex.: $\log n \in O(\sqrt{n}), \sqrt{n} \in O(\sqrt{n}) \implies \sqrt{n} \log n \in O(n)$

- **Transitivity**: $d(n) \in O(f(n)), f(n) \in O(g(n)) \implies d(n) \in O(g(n))$.
  📝 Ex.: $\log n \in O(\sqrt{n}), \sqrt{n} \in O(n) \implies \log n \in O(n)$

📌 Note: these rules are an alternative way to the definition for determining the asymptotic notation of functions.
