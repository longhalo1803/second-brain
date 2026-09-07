---
title: "How important is the efficiency (and speed) of algorithms Give an example"
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
  - "How important is the efficiency (and speed) of algorithms Give an example"
---

# 🎴 How important is the efficiency (and speed) of algorithms Give an example

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: How important is the efficiency (and speed) of algorithms? Give an example #card

?
This simple example illustrates it well, where we run an efficient algorithm on a slow computer 🆚 an **inefficient** algorithm on a fast computer:

Problem input: `n` integers

      EFFICIENT Algorithm:
      requires n² elementary operations to solve the problem


        SLOW Computer:

      executes 10³ op/sec



      INEFFICIENT Algorithm:
      requires 2ⁿ elementary operations to solve the problem


        FAST Computer:

      executes 10⁷ op/sec






        n
        Efficient Algorithm Time
        INEFFICIENT Algorithm Time




        10
        10² * 10⁻³ = 0.1 sec
        2¹⁰ * 10⁻⁷ = 0.0001 sec 🥇


        20
        20² * 10⁻³ = 0.4 sec
        2²⁰ * 10⁻⁷ = 0.1 sec 🥇


        30
        30² * 10⁻³ = 0.9 sec 🥇
        2³⁰ * 10⁻⁷ = 17.9 min 🐢


        > 30
        ... 🥇
        🐢
