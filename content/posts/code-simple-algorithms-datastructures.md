---
date: '2025-06-05T08:04:30+10:00'
title: 'Code Simple Algorithms and Data Structures (from scratch for fun)'
---

Vibe coding is amazingly productive, at least for experiments and prototypes.

And fun.

Recently, I've noticed something missing. A feeling.

The feeling you get when thinking hard while crafting a piece of code. Of desk checking it in your head. Of thinking through edges cases.

I'm missing the feeling of making my brain sweat while crafting some code.

I had an idea:

> Why not code up simple algorithms and data structures from scratch for "fun"?

I'm thinking of the stuff from "intro to algorithms and data structures" in compsci. Things like linked lists, hash tables, quick sort, design patterns, etc. that I have not implemented by hand for 25+ years.

Why not code up simple algorithms and data structures as an exercise to capture that brain sweat feeling I'm missing.

I talked it over with grok3 and we came up with the idea of the user (me) working from a terse description and a template of the algorithm/data structure interface and working until a set of comprehensive pre-defined unit tests pass.

I tried this and immediately got stumped. Stupid atrophied brain, get better!

So in addition, on offer are also hints on how to think about the implementation of each piece of the template interface, in English prose. These hints help a lot, and can even be a crutch. Use sparingly.

And this is all in Python, because fun++.

So, you get:

1. A terse description
2. An interface to implement.
3. Unit tests to test the interface implementation.
4. Plain English hints for the interface.

And it's great.

It's exactly what I need.

I've completed a linked list and am currently working through a hash table.

Next, trees, sorts, searches, maybe even move into optimization and ml algorithms, because fun.

I found it useful to debug specific use cases when things aren't working (e.g. in a "main"). I also found it helpful to drop the whole implementation into gpr4o/claude4 afterward and ask for a critique, e.g. to tighten the code and pythonic-ness.

I'm also thinking of pushing these exercises to a hugo book structure, in case others want to have have a go.

The resulting implementations will sit on disk. They are not for anything other than pure joy/hobby/brain sweat.

I was thinking of calling it something like _Programmer Atrophy Gym_ or something.

So cool.

One could imagine a platform that you code in directly and run unit tests in the browser, track score/progress, etc. Sure, a bit heavy for now.

The simplest version is static. If that is fun enough, expand later if there's any interest.

For now, one-at-a-time template generation and manual completion, just for me.

This all has the smell of [algorithm afternoon](https://algorithmafternoon.com/), but for compsci and with unit tests.