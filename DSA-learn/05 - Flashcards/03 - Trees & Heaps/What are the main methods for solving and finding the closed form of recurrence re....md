---
title: "What are the main methods for solving and finding the closed form of recurrence re..."
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
  - "What are the main methods for solving and finding the closed form of recurrence re..."
---

# 🎴 What are the main methods for solving and finding the closed form of recurrence re...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What are the main methods for solving and finding the **closed form** of **recurrence relations**? #card

?
The three main approaches analyzed are:

- **Iterative method**: The equation is "unrolled" by repeatedly replacing $T$ with its expansion in terms of itself until reaching the base case. It typically reduces the function to a **known numerical series** (e.g., sum of the first $k$ squares, geometric series). Used in Factorial, Fibonacci, and Tower of Hanoi.
- **Substitution method (Induction)**: Consists in guessing a specific closed form for the solution ("guessing" phase), and then proving via the **principle of mathematical induction** that the hypothesis is correct for every input value (e.g., to formally prove that $M(m) = 2^m -1$ for Hanoi).
- **Master Theorem**: A pre-packaged, analytical "template" to immediately derive the asymptotic notation $O(\cdot)$ of **algorithms based on the Divide and Conquer technique** with a recurrence relation of the form $a \cdot T\left(\frac{n}{b}\right) + c_2 \cdot n^d$. It derives the bound by comparing the division/combination cost against the volume of sub-calls.

- [ADVANCED] **Recursion-Tree Method**: allows visualizing graphically the development of the computational cost of a recursive algorithm, making its evaluation easier. Each node in the tree is associated with the solution of the problem for a given input size. The root is associated with the problem for input size equal to $n$. Each node has as many children as there are recursive calls. When the problem size falls into the base case of the equation, the node becomes a leaf and, therefore, has no children.
  The complete tree is built by associating with each node where a recursive call appears the cost relative to the problem with that specific input size, and adding the appropriate child nodes. Construction ends when all recursive calls have been examined and the leaves of the tree refer only to problems that fall into the base case.
  The computational cost of the algorithm is calculated by summing the computational costs associated with the nodes of the tree. To facilitate this calculation, it is helpful to establish how many levels the tree has and how many nodes are at each level.
