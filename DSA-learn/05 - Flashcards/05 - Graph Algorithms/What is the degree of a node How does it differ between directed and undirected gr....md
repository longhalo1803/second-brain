---
title: "What is the degree of a node How does it differ between directed and undirected gr..."
tags:
  - dsa
  - flashcards
  - clrs
  - graphs
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the degree of a node How does it differ between directed and undirected gr..."
---

# 🎴 What is the degree of a node How does it differ between directed and undirected gr...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the degree of a node? How does it differ between directed and undirected graphs? #card

?
The **degree** indicates the number of connections attached to a given node.

**Undirected graph:** the degree of a node $v$ ($\text{deg}(v)$) is the number of edges $(v,u) \in E$ incident to $v$.

**`deg(3) = 3`**

**Directed graph:** two metrics are distinguished:

• **In-degree (**$\text{in-deg}(v)$**):** number of edges incoming to $v$, i.e., of the form $(u,v) \in E$.
• **Out-degree (**$\text{out-deg}(v)$**):** number of edges outgoing from $v$, i.e., of the form $(v,u) \in E$.

**`in-deg(3) = 2, out-deg(3) = 1`**
