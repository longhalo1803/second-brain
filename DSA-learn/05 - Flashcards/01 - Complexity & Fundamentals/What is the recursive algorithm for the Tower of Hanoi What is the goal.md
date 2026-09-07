---
title: "What is the recursive algorithm for the Tower of Hanoi What is the goal"
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
  - "What is the recursive algorithm for the Tower of Hanoi What is the goal"
---

# 🎴 What is the recursive algorithm for the Tower of Hanoi What is the goal

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is the recursive algorithm for the **Tower of Hanoi**? What is the goal? #card

?
The goal of the Tower of Hanoi is to move $m$ disks from the source peg ($s$) to the destination peg ($d$) using an auxiliary peg ($a$), moving one disk at a time without ever placing a larger disk on a smaller one.

The recursive idea is to move the top $m-1$ disks onto the auxiliary peg, move the last (largest) disk to the destination, and move the $m-1$ disks from the auxiliary peg to the destination.

📝 Example:

$m$: number of disks
$s$: source peg
$d$: destination peg
$a$: auxiliary peg

```text
Hanoi(m, s, d, a)
    if m = 1                             // base case
        then MoveOneDisk(s, d)
    else                                 // recursive case
        Hanoi(m - 1, s, a, d)                // move m-1 disks from source to auxiliary
        MoveOneDisk(s, d)                    // move the last disk to destination
        Hanoi(m - 1, a, d, s)                // move m-1 disks from auxiliary to destination
```

Cmglee, CC BY-SA 3.0, via Wikimedia Commons
