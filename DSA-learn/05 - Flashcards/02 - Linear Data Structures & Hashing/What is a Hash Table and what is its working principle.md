---
title: "What is a Hash Table and what is its working principle"
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
  - "What is a Hash Table and what is its working principle"
---

# 🎴 What is a Hash Table and what is its working principle

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is a **Hash Table** and what is its working principle? #card

?
A **hash table** is a data structure that stores pairs $(k, v)$ inside an array $H[0 \dots m-1]$ of size $m$.

The key principle is that the **position (index)** at which to store or search for the pair $(k, v)$ within $H$ is neither arbitrary nor sequential, but depends directly on the key $k$ itself.

A **hash function** $h$ is used to compute the cell index:

$$

h: U \to \{0, 1, \dots, m-1\}

$$

$$

\text{index} = h(k)

$$

The pair $(k, v)$ is then allocated in cell $H[h(k)]$.
