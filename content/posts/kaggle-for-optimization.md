---
date: '2025-06-02T09:23:36+10:00'
title: 'Kaggle for Optimization Problems'
---

Back in grad school days, it was fun to pick NP-Complete optimization problems and have little competitions to see who could get the best solution (lowest cost) in a given time frame.

One of the more popular competitions we had was made semi-formal called maxpath:

* [Max Path](https://github.com/Jason2Brownlee/MaxPath)

Pic:

![max path](https://raw.githubusercontent.com/Jason2Brownlee/MaxPath/main/grid.jpg)

I've always enjoyed optimization more than machine learning.

I remember having coffee with Kaggle's [Anthony Goldbloom](https://en.wikipedia.org/wiki/Anthony_Goldbloom) circa 2010 and saying that he should add competitions for optimization problems. It wasn't a good fit.

The idea came back to me today.

I was chatting with grok3 about the computational complexity for a dynamic programming algorithm for the problem.

There's no reason why we couldn't vibe code a simple "**Kaggle for NP-Complete Optimization Problems**".

For example:

- Problems are well defined such that they cannot be brute forced without hundreds of years of 2025-level compute.
- Users submit candidate solutions that are evaluated server side and scored and ranked (very simple/fast).
- Leaderboards show what has been achieved (can be achieved) for given problems with cumulative scores across problems.

Solutions could be public or private. If public, one can imagine downloading and local-searching for rapid leader board hill climbing. Helpful if the problem is really hard or solutions are time sensitive.

I guess businesses could submit really hard problems for public solution, e.g. fixed-length competitions to get fast/efficient algorithms. The goal would be to hiring optimization geeks or get fast code for common problems run in the org.

Not sure that companies will do that though. Most interesting NP-Complete problems have a time factor and involve fast implementations well known algorithms. Innovation in this area comes from math, not code. At least that is my guess.

My guess is that stuff like this is already part of larger competition coding platforms. I'm just not across them.

I was thinking that it would be more of a fun house for stochastic optimization algorithm practitioners and hobbyists to try out their wares.

The effort is low to get a prototype of this going for maxpath running on netlify with python/sqlite.

meh.