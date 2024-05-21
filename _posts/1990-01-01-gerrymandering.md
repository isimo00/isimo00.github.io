---
layout: post
title: Gerrymandering 
date: 1990-01-01 17:39:00
tags: formatting diagrams
description: Exploration of the political districting problem
mermaid:
  enabled: true
  zoomable: true
---

# Gerrymandering or Political Districting

The "Masachussetts Problem"

_Gerrymandering_ is the practice of partitioning a graph in I have modelled this problem from three different perspectives:

1. Creating an heuristic that finds a gerrymandered solution given an initial district map
2. Defining a combinatorial (optimization) problem
3. Defining game theory dynamic

## 1. Heuristic
I designed and implemented a smart version of a greedy algorithm for faster convergence of a satisfactory partition. 

I first mapped the typical electoral map to a graph in such a way that each district is a connected component. This implies the decision variables of our problem are edges; removing and adding edges can

Here are the slides of a very short presentation I created to explain how the heuristic works

<object data="{{ site.url }}{{ site.baseurl }}/assets/pdf/g.pdf" width="1000" height="500" type="application/pdf"></object>

## 2. Combinatorial problem
The translation of an electoral map to a lattice graph, as previously stated, naturally positions the focus of the problem on the edges. With this, the most natural choice for our decision variables is to use the adjacency matrix of such graph $$A$$. Moreover, given that the graph is a lattice, the matrix will present a certain structure. For instance, for a $$3x2$$ grid, labeled from left to right by rows,

$$A=\begin{pmatrix}0 & 1 & 0 & 1 & 0 & 0\\
                   1 & 0 & 1 & 0 & 1 & 0\\
                   0 & 1 & 0 & 0 & 0 & 1\\
                   1 & 0 & 0 & 0 & 1 & 0\\
                   0 & 1 & 0 & 1 & 0 & 1\\
                   0 & 0 & 1 & 0 & 1 & 0\\
\end{pmatrix}$$

Here we see that the only edges we would consider removing are those with a 1. For a $$nxn$$ matrix:

$$
\begin{cases}
1 & \text{if } |i - j| = 1 \text{ and } i \div n = j \div n \\
1 & \text{if } |i - j| = n \\
0 & \text{otherwise}
\end{cases} 
$$

## 3. Game theory dynamic
_Consider the graphical game in which we have a set $$E(G)$$. A player $$e=(i,j)$$ can choose to exist $$a_{i,j}=1$$ or not exist $$a_{i, j}=0$$. For a given profile $$s=(s_1, ..., s_{|E|})$$, let $$G[S]$$ be the undirected graph formed by the $$C$$ connected components $$G[S]=\cup_{c\in C}G[S]_c$$ induced by the player's decisions. Let us also define a mapping $$p:V\rightarrow\{-1, 1\}$$, with vertices $$v(p)=1$$ being voters of the party we want as winner. We define the value of a connected component $$P:G[S]\rightarrow\{-1, 1\}$$ as the sum of the mapping of its vertices. The cost for player $$e\in E$$ is defined as:_

$$c_{e}(s)=|\{G[S]_c \in C| G[S]_c (P)\geq 0 \}|$$

Metrics like the Price of Stability, Price of Anarchy and other game theory related indicators are also interesting for this problem.
