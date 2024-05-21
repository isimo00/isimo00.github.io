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

Here are the slides of a very short presentation I created to explain how the heuristic works

<object data="{{ site.url }}{{ site.baseurl }}/assets/pdf/g.pdf" width="1000" height="1000" type="application/pdf"></object>

