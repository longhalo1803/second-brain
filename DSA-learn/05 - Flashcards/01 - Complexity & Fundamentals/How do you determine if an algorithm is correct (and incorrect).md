---
title: "How do you determine if an algorithm is correct (and incorrect)"
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
  - "How do you determine if an algorithm is correct (and incorrect)"
---

# 🎴 How do you determine if an algorithm is correct (and incorrect)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: How do you determine if an algorithm is correct (and incorrect)? #card

?
One would need to prove that for every input (every instance of the problem to be solved) the correct output corresponds, but in most cases that would be an infinite process.
Following the principles of logic, the equivalent is to show that there exists at least one case in which the algorithm does not work/does not hold, in order to prove that it is incorrect.

```text
{≠g x \, P(x)}_{does not hold in all cases} {}_{if and only if} { x \, ≠g P(x)}_{there exists a case in which it does not hold}
```

[in other words]
An **example **showing that the output is as expected given a certain input is **not enough**.
A **counterexample **is **enough** to prove the NON-correctness of an algorithm.
