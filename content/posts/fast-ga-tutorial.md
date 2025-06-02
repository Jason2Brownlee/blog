---
date: '2025-06-03T07:53:01+10:00'
title: 'Fast Genetic Algorithm Tutorial/Book'
---

A while back I showed how we can get a genetic algorithm in Python to run as fast then faster than a naive implementation in C.

Here it is:

* [Fast Genetic Algorithm in Python](https://github.com/Jason2Brownlee/FastGeneticAlgorithm)

It was fun little project that mainly consisted of lots of timeit tests of different numpy functions and different ways of vectorizing the operations.

The project was not very didactic. More of a progression. A show and tell.

I was thinking, it might be fun to re-do-it as a long tutorial.

To organize tests/experiments into clusters and show a progression through different optimizations. And also to be more systematic with the benchmarking.

It would make a fun little technical tutorial or book(let).

Probably a free [hugobook](https://github.com/alex-shpak/hugo-book) with complementing kindle and paperback versions, because: why not.

What could the sections/organization be?

- Project Objective
- Simple Genetic Algorithm
- Benchmarking
- GA in ANSI C
	- Functions
	- Single Function
- GA in Vanilla Python
	- Functions
	- Single Function
- GA in NumPy Python
	- Functions
	- Single Function
	- Change Data Types
	- Pre-Allocate/Reuse memory
	- Vector Bitstring vs Matrix Population
	- Pre-compute Choices/Random Numbers
	- Vectorization

Then perhaps other things I didn't get to, like JIT, Threads, Cython, etc.

It could be fun.

Then you could also throw an LLM at it. E.g. seed with everything tried and some books on Python performance hacking and see what other ideas it has.

Would anyone ever find this interesting, and if so why?

- Learn about GAs?
- Learn about Python/NumPy performance optimization?
- It's fun?

Need to think on it. Might take a few weeks to put something good together, it's no whim.