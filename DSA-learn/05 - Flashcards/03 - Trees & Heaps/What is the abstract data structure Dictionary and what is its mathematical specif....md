---
title: "What is the abstract data structure Dictionary and what is its mathematical specif..."
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
  - "What is the abstract data structure Dictionary and what is its mathematical specif..."
---

# 🎴 What is the abstract data structure Dictionary and what is its mathematical specif...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the abstract data structure **Dictionary** and what is its mathematical specification? #card

?
A **dictionary** is an abstract data type (ADT) that implements the mathematical concept of a **unique relationship** (or partial function):

$$

r: D \to C

$$

between the elements of a **domain** set $D$ (called **KEYS**) and the elements of a **codomain** set $C$ (called **VALUES**).

It stores a set of pairs of the form:

$$

(\text{KEY}, \text{VALUE})

$$

where the pairs are uniquely indexed by the key, while the associated value represents _satellite data_ (useful information linked to the key).

📝 Example: in graphs, if nodes are not numbered from $1$ to $n$ but instead correspond to city names, a dictionary maps each city to its corresponding index or record. Other examples include `(name, phone number)` directories or `(IP address, user)` associations.
