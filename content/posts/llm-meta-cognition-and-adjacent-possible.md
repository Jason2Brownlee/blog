---
date: '2025-01-29T09:09:10+11:00'
title: 'LLM Meta-Cognition and Exploring the Adjacent Possible'
---


Andrej Karpathy has a wonderful tweet on what he calls learned "cognitive strategies" but I think more generally is referred to as "meta cognition".

The piece I like is:

> ...The models discover, in the process of trying to solve many diverse math/code/etc. problems, strategies that resemble the internal monologue of humans, which are very hard (/impossible) to directly program into the models. I call these "cognitive strategies" - things like approaching a problem from different angles, trying out different ideas, finding analogies, backtracking, re-examining, etc. Weird as it sounds, it's plausible that LLMs can discover better ways of thinking, of solving problems, of connecting ideas across disciplines, and do so in a way we will find surprising, puzzling, but creative and brilliant in retrospect...

Here's the [full tweet](https://x.com/karpathy/status/1884336943321997800):

{{< twitter user="karpathy" id="1884336943321997800" >}}

Fantastic tweet.

Apt as we all get to peer into DeepSeek's reasoning traces and think about the possibilities.

I have been thinking a lot about this and am pretty convinced that although LLMs are generally [stuck in-distribution](/blog/posts/llm-in-distribution/), that the distribution so large and so rich that there a vast number of innovations available to mine (e.g. via [idea-sex](/blog/posts/conceptual-blending/) across domains and [learning intuitive physics](/blog/posts/ai-intuitive-physics/) in non-intuitive domains).

Maybe we just need to know the right questions to ask (and [how to ask them](/blog/posts/llm-prompt-optimization/)).

Wow, cool! Innovation is open to even dumb-dumb's like me :)

Here's gpt4o's take on this snippet of the tweet:

> The idea that LLMs "discover" cognitive strategies in their attempt to solve diverse problems highlights the principle of emergent behavior. By not being explicitly programmed to reason in specific ways, these models instead "learn" to approximate complex reasoning processes by analyzing patterns in data. This is similar to how humans develop metacognitive strategies (like analogical thinking or backtracking) as we engage in problem-solving.
>
> This emergent behavior is fascinating because it suggests that AI might evolve ways of reasoning or solving problems that deviate from traditional human approaches but are nonetheless effective, even groundbreaking. For example, an AI might use highly non-intuitive analogies or leapfrog steps humans might overlook due to cognitive biases or cultural frameworks.

I'm reading books on innovation atm and this tweet got me thinking about the "adjacent possible" from the study of evolution and borrowed in the study of innovation.

From our friend, claude:

> The **adjacent possible** is a concept introduced by theoretical biologist Stuart Kauffman that describes the potential next steps that can emerge from the current state of a system. It suggests that innovation and change happen through small, achievable steps from what currently exists, rather than through giant leaps.

Nod.

There are concepts and artifacts right there, just at the tips of our fingers.

All we have to do is reach a little further.

Here's gpt4o on this notion:

> The adjacent possible describes the expanding frontier of what can be achieved, given the current state of knowledge and resources. LLMs, with their vast training corpora, effectively inhabit a much broader adjacent possible because they can combine and recombine ideas from disparate domains that humans may not intuitively link.
>
> By processing vast amounts of data and synthesizing patterns across disciplines, LLMs can uncover latent connections that resemble innovation. These connections might include:
>
> * **New theories or hypotheses**: AI might identify subtle correlations across datasets that humans haven’t noticed.
> * **Interdisciplinary breakthroughs**: By blending knowledge from multiple fields, LLMs could propose solutions to problems in ways no single expert would consider.
> * **Novel representations of problems**: Reframing a question or problem can sometimes unlock answers, and LLMs seem adept at offering alternative framings.

Nod, this:

* "...LLMs [...] inhabit a much broader adjacent possible because they can combine and recombine ideas from disparate domains that humans may not intuitively link..."

And:

> Human reasoning is constrained by our mental heuristics, biases, and prior experiences. In contrast, LLMs can traverse solution spaces in ways that might seem odd, inefficient, or even nonsensical to us—but which yield valid and valuable results. For example:
>
> * They might explore tangents that humans would dismiss as irrelevant but which prove to be fruitful.
> * They might apply reasoning strategies that are mathematically sound but lack an intuitive human explanation.
> * They may also "rediscover" historical ideas or methods that have been forgotten or neglected.
>
> Such capabilities suggest that LLMs are not merely tools but collaborators in innovation, capable of proposing ideas we might not arrive at independently.

Nice. Agreed.

So, we _could_ get to places in the human-written-workproduct latent space via force-optimized reasoning strategies that we (humans) may naively dismiss, or lack intuition, or neglected. Sign me up!

But gpt4o always seems to tell me what I want to hear.

I think this is related to Will Bryk's idea of "[superknowledge](https://exa.ai/blog/superknowledge)" instead of superintelligence, except...

His definition is good, but I don't care about the problems he's interested in.

For example:

> **Superknowledge** is a system that can handle extremely complex **retrieval** requests.

And:

> Superknowledge would handle requests like:
> "all physics PhDs in NYC" (should return all 457 physics PhDs in NYC and any associated metadata)

Don't care.

I want my "complex retrieval request" to 1) be across domains of knowledge and 2) using a suite of meta-cognitive strategies "evolved" by forcing reasoning LLMs to solve a ton of hard problems that are interesting to humans.

Anyway, how might we start mining the adjacent possible for cool, interesting, and even useful things?

Let's assume we're focused on a domain in which we have expertise. Let's pick programming/ml/concurrency/etc. the usual.

We don't want, "optimize my algorithm in a clever way", but some steps beyond, e.g. perhaps "a new algorithm that borrows an idea from way over there".

Let's figure out what an "adjacent possible" innovation is fist.

Response dump from our old friend, claude:


> 1. Normal Problem Solving
> - Working within established patterns and known solutions
> - Example: Implementing a binary search tree or optimizing a SQL query
> - You're operating within well-defined constraints and patterns
> - The solution space is relatively bounded and known
>
> 2. Solution Iteration/Optimization
> - Taking an existing solution and improving its performance or characteristics
> - Example: Converting a recursive algorithm to iterative, or parallelizing a sequential process
> - You're still working within the same fundamental approach
> - Innovation happens through refinement rather than paradigm shifts
>
> 3. **Adjacent Possible Innovation**
> - Combining existing concepts in novel ways or applying patterns from one domain to another
> - Example: When MapReduce took the functional programming concepts of map and reduce and applied them to distributed computing
> - You're creating something new, but it's built directly from existing components or concepts
> - The innovation is "one step away" from current knowledge
>
> 4. Architectural Innovation
> - Rethinking how existing components or concepts can be reorganized
> - Example: How microservices architecture emerged from SOA principles
> - You're not inventing new components, but reorganizing them in fundamentally different ways
>
> 5. Paradigm Extension
> - Taking an existing paradigm and extending it into new territory
> - Example: How reactive programming extended functional programming concepts into event-driven systems
> - You're pushing the boundaries of an existing paradigm rather than creating a new one
>
> 6. Breakthrough Innovation
> - Creating genuinely new paradigms or approaches
> - Example: The initial development of blockchain technology
> - While still built on existing knowledge, it represents a larger conceptual leap
>
> The key distinction with the adjacent possible is that it's specifically about innovations that are one step removed from current reality - they're achievable because all the prerequisites exist, but they haven't been realized yet.
>
> In your domains, the adjacent possible might look like:
> - ML: Applying a successful architecture from one domain (say, image recognition) to a novel domain where it hasn't been tried
> - Concurrency: Combining patterns from different concurrency models in novel ways
> - Programming: Creating new abstractions that bridge gaps between existing paradigms
>
> The most fertile ground for adjacent possible innovations often lies at the intersections of your areas of expertise - where concurrency meets ML, or where programming paradigms meet distributed systems. These intersection points often have unexplored territory that's accessible with current knowledge but hasn't been fully investigated.

(should have included more "areas of expertise/interest" in the query...)

This:

> You're creating something new, but it's built directly from existing components or concepts. The innovation is "one step away" from current knowledge.

Exactly.

Am I thinking too small?

I'm a simple man. Exploring the "Adjacent Possible" sounds fine+fun. I'm not building unicorns here. Nominally retired/sabbatical, remember.

What are some "map reduce + distributed computing" type ideas we can mine using o1/o3/R1/etc.?

Side thought, I always felt that DeepMinds RL+Atari felt like one of these. Clever, (and they nobel-level-clevel fellows) but an adjacent first project.

So, methodology.

I asked gpt4o for some ideas, and got the usual. Good advice, but bland.

For example:

> * Divergent Thinking Prompt: “Generate 5 unconventional ways to approach the problem of [X] by drawing analogies from unrelated fields, such as biology, engineering, or art.”
> * Analogical Reasoning Prompt: “Explore how [concept] in [domain A] could be applied to solve [problem] in [domain B].”
> * Self-Reflective Prompt: “Analyze your previous answer critically. Identify potential weaknesses or assumptions and propose alternative approaches.”

And on.

What's key here is that ~~no one knows~~ [few people know](https://www.latent.space/p/o1-skill-issue) how to drive reasoning models well. Experimentation is required.

Also, one step is so small. How do you know when you've got it? (you're a domain expert for the problem, I guess it'll be obvious). Feels a little non-falsifiable to me.

We'll all be hill climbing the adjacent possible (to local minima) for fun and profit before you know it!



