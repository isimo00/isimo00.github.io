---
layout: post
title: Gossiping in social networks 
date: 1990-01-01 17:39:00
tags: formatting diagrams
description: Some informal exploration of gossip spread using Random Hyperbolic Graphs (RGHs)
mermaid:
  enabled: true
  zoomable: true
---

# Gerrymandering or Political Districting

I have modelled this problem from three different perpsectives:

1. Creating an heuristic that finds a gerrymandered solution given an initial district map
2. Defining a combinatorial (optimization) problem with a SAT formulation
3. Defining game theory dynamic

# Gossiping

The gossiping problem was proposed originally as follows \cite{baker1972gossips}:

    There are $n$ ladies, and each of them knows some item of gossip not known to the others. They communicate by telephone, and whenever one lady calls another, they tell each other all that they know at that time. How many calls are required before each gossip knows everything?
    
If we set the number of gossips to 1, this is equivalent to broadcasting. Now, intuitively, celebrities or __influencers__ should be the most effective sources of gossip to optimize the spread speed, right? But if we are trying to promote our friend's business, getting a "big" celebrity to talk about it might be unfeasible. Rather, we could think of contacting a few, less-known micro-celebrities. Maybe if we do that skillfully enough, we might be even able to spread our message even faster than if we contacted the big celebrity to begin with!

We want to focus on this new optimization problem. How many, how popular celebrities would be optimal for our gossiping or broadcasting scenario?

We will define the cost of getting someone to spread our gossip as their degree.
