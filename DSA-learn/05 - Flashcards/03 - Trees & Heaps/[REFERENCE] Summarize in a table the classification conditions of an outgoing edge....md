---
title: "[REFERENCE] Summarize in a table the classification conditions of an outgoing edge..."
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
  - "[REFERENCE] Summarize in a table the classification conditions of an outgoing edge..."
---

# 🎴 [REFERENCE] Summarize in a table the classification conditions of an outgoing edge...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: [REFERENCE] Summarize in a table the classification conditions of an outgoing edge $(u,v)$ during a DFS traversal on a directed graph. #card

?
Edge typeTime conditionRelationship between $u$ and $v$Indicates a cycle?**TREE**$\textsf{pre}[v] = 0$$v$ is discovered by $u$No**BACK**$\textsf{pre}[v] $v$ is an **ancestor** of $u$**YES ⚠️****FORWARD**$\textsf{pre}[v] > \textsf{pre}[u] \land \textsf{post}[v] > 0$$v$ is a **descendant** of $u$No**CROSS**$0 Neither ancestor nor descendantNo
