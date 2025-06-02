---
date: '2025-06-03T05:59:04+10:00'
title: 'AlphaEvolve'
---

I was thinking about DeepMinds AlphaEvolve from last month.

It's pretty cool. The results are cool. The overall structure is pretty straightforward-ish though. As in, it did not surprise me very much.

* [AlphaEvolve: A Gemini-powered coding agent for designing advanced algorithms (announcement)](https://deepmind.google/discover/blog/alphaevolve-a-gemini-powered-coding-agent-for-designing-advanced-algorithms/)
* [AlphaEvolve: A coding agent for scientific and algorithmic discovery (paper, pdf)](https://storage.googleapis.com/deepmind-media/DeepMind.com/Blog/alphaevolve-a-gemini-powered-coding-agent-for-designing-advanced-algorithms/AlphaEvolve.pdf)
* [AlphaEvolve, Wikipedia](https://en.wikipedia.org/wiki/AlphaEvolve)

Here's how I'm thinking about it.

It's a GA with LLM operators. Something that many people have been trying, but have not unlocked this well, so far.

One thing I did think was quite interesting was that the evolutionary algorithm's population is a mess, e.g. not a clean classical EA population structure. It's geared up for controlled diversity and fast convergence:

> During its evolutionary procedure, AlphaEvolve continually generates a growing number of solutions with evaluation results (scores and program outputs) attached to them. These solutions are stored in an evolutionary database, the primary goal of which is to optimally resurface previously explored ideas in future generations. A key challenge in designing such databases is balancing exploration and exploitation, to continuously improve the best programs while maintaining diversity to encourage exploration of the entire search space. In AlphaEvolve, the evolutionary database implements an algorithm that is inspired by a combination of the MAP elites algorithm [73] and island-based population models [82, 96].

So it's resampling variations on historically good candidate solutions, e.g. map elites.

Anyway, here's my (possibly too simple) pseudocode sketch of the main loop:

```python
# Initialize program database with initial candidate(s)
program_database = initialize_database(initial_program)

while not termination_condition:
    # 1. Sample a parent program and inspirations from database
    parent_program, inspirations = program_database.sample()

    # 2. Build prompt using prompt sampler
    prompt = build_prompt(parent_program, inspirations)

    # 3. Generate code diff using LLM ensemble
    diff = llm_ensemble.generate(prompt)

    # 4. Apply diff to get new child program
    child_program = apply_diff(parent_program, diff)

    # 5. Evaluate the new program (possibly in parallel)
    score = evaluate(child_program)

    # 6. Store the new program and its score
    program_database.add(child_program, score)

    # Optionally: prune or resample database to balance exploration vs exploitation
```

All operators are LLM-driven, and the operators are a mess too. For example synthesis involves generating many candidate ideas based on the database of past solutions, e.g. "thing to try".

> As AlphaEvolve leverages SOTA LLMs, it supports various types of customization and providing long contexts as part of the primary evolution prompt. This prompt comprises multiple previously discovered solutions sampled from the program database, as well as system instructions on how to propose changes to a particular solution

It can also sample prompts that give ideas of synthesis prompts to try, e.g. meta prompting.

The directed evolutionary search is important to the process. Ablation studies that removed it did not do as well. But I'm guessing that any directed stochastic search algorithm could be used in it's place.

Importantly, the focus is on code, on operators that synthesise and select programs (or the effect of diffs on programs). This makes it different from Google's [AI Co-Scientist](https://research.google/blog/accelerating-scientific-breakthroughs-with-an-ai-co-scientist/) work.

Both projects have a touch of Rube-Goldberg agent messes at the moment. Maybe all of this will move into the model, e.g. rather than "take on the persona of an agent..." it will be "Take on the persona of the agent collective..."

Interestingly, give the breadth of problems they tried, this forced them to explore alternate representations, e.g. direct solution (program), function to construct the program, and search algorithm to find the program.

> Interestingly, AlphaEvolve often allows approaching the same problem in different ways: searching for the solution directly, finding a function that constructs it from scratch, or evolving a search algorithm to find it. Applying AlphaEvolve in different ways comes with different biases (for example, finding constructive functions may favor discovering highly symmetric objects [82]) and thus can suit different problems.

This all seems like fun stuff.

There's an open source effort reproducing the method here:

* [OpenEvolve](https://github.com/codelion/openevolve)