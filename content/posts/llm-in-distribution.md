---
date: '2025-01-28T09:46:32+11:00'
title: 'Are LLMs Stuck In-Distribution?'
---

Machine learning models have an [IID assumption](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).

That is data on which they are trained must be representative of data on which they will make predictions on later.

The big question is AI is:

* Are generative models capable of generating data out of distribution?

Naively, ~~we~~ I think **no**.

But there data distribution is so vast that it's hard to see at first.

For example, an image generation model can interpolate within the space of ~~all~~ most images on the net.

An LLM can interpolate within the space of all digitized text that OpenAI and Anthropic can get their hands on.

Big spaces. Interpolation can get you a long way. It can also result in hallucinations in parts of the space that are data-poor.

As such, many older-school ML/AI people dismiss the capability of new knowledge creation/innovation by LLMs/generative models.

Fair.

But is that right? I'm not up to date on the literature, but last time I checked, it was very hard to determine.

I sometimes hear this argument (_LLMs can are limited to in-distribution responses_) used by "ML experts" to dismiss all LLM output.

This (wholesale dismissal) is wrong. They can do some wild and seemingly clever stuff that _looks_ out of distribution to a dumb dumb like me.

Here's a morning thought though:

We keep scaling, we keep training, and eventually the models [grok](https://en.wikipedia.org/wiki/Grokking_(machine_learning)) the [underlying physics](/blog/posts/ai-intuitive-physics/) of how human thinking works via our vast archives of language work product.

I guess that's what the optimists are hoping.

I note that specifically this case was one of the [warning signs quipped by Eliezer Yudkowsky](https://x.com/ESYudkowsky/status/1650888567407902720), e.g. a dramatic drop in validation loss as a sign of hard and fast take off (FOOM):

> ...Possible but hardly inevitable.  It becomes moderately more likely as people call it absurd and fail to take precautions against it, like checking for sudden drops in the loss function and suspending training.  Mostly, though, this is not a necessary postulate of a doom story.

I had a talk with gpt4o/claude/perpexity about LLM's outputting text in-distribution and out of distribution and evidence for and against.

Not a lot of compelling stuff I'm sad to say.

> Large Language Models (LLMs) can generate text that appears to be "out of distribution" to some extent, but their ability to do so is limited. While LLMs have learned to generalize and combine information in novel ways, they struggle with true out-of-distribution (OOD) tasks, especially those requiring reasoning and problem-solving skills

And:

> While LLMs have learned to generalize and combine information in impressive ways, their ability to handle true OOD tasks remains limited. They are not "just memorizing" their training data, but their generalization capabilities are constrained to areas adjacent to or near their training distribution

About what one would think from first principles.

This line of thinking on "_unambiguous signs that llms are able to generate out of distribution responses/text/knowledge_" with gpt4o was interesting:


> Unambiguous signs that LLMs are capable of generating **out-of-distribution (OOD)** responses or text would involve demonstrating that they can consistently perform well in contexts or tasks that are definitively outside the scope of their training data or statistical patterns. This would require evidence that they go beyond the limits of interpolating or recombining in-distribution knowledge. Here are some clear indicators:
>
> ### 1. **Novel Conceptual Synthesis**
> An unambiguous sign would be the generation of text that reflects a deep understanding or synthesis of concepts **not found in the training data**, such as:
> - Proposing original scientific theories that are later validated empirically.
> - Formulating entirely new philosophies or systems of thought that are unrelated to pre-existing knowledge.
> - Creating coherent and innovative text about topics for which there is no close analogue in the training distribution (e.g., describing a novel type of mathematics that didn’t exist before).
>
> **Example Test**: Ask the model to write about a hypothetical universe governed by physics laws completely unlike anything in our universe, where no related examples exist in the training data.
>
> ### 2. **Generalization to New Domains**
> Performance in tasks that:
> - Require reasoning in **unseen modalities** or **new combinations of concepts** outside their training distribution.
> - Successfully tackling real-world scenarios that have no precedent in training data, such as entirely new technologies, events, or societal structures.
>
> **Example Test**: Present the model with a set of instructions for a game invented after the training cutoff and observe if it can reason about gameplay or generate strategies without prior exposure.
>
> ### 3. **Robustness to Adversarial Inputs**
> LLMs often fail or hallucinate when faced with adversarial inputs that intentionally break the structure of familiar training patterns. A model capable of generating OOD responses would:
> - Handle nonsensical or intentionally adversarial inputs with clarity, robustness, and reasoned extrapolation.
->  Avoid reverting to in-distribution biases or hallucinations and instead provide responses grounded in abstract reasoning.
>
> **Example Test**: Query the model with a deliberately contradictory or nonsensical prompt like "In a universe where up is down and circles are square, how does light travel?" and assess whether it can logically extrapolate rather than default to learned patterns.
>
> ### 4. **Accurate Responses to Future Knowledge**
> A compelling demonstration of OOD capability would involve the ability to:
> - Accurately predict or extrapolate knowledge **beyond its training cutoff date** or existing datasets.
> - Infer new scientific discoveries, technological advances, or sociopolitical events based solely on prior trends, without direct exposure.
>
> **Example Test**: If a scientific breakthrough occurs after the training cutoff, evaluate whether the model can reason about its implications or plausibly infer its outcomes before being fine-tuned on newer data.
>
> ### 5. **Language Creation and Generalization**
> If an LLM could:
> - Generate entirely new languages with well-defined grammar, syntax, and semantics, not based on interpolation from existing languages.
> - Generalize linguistic principles to unstructured or novel communication systems (e.g., inventing a new programming language from scratch and demonstrating its utility).
>
> **Example Test**: Ask the model to create a functional language for communication among species with non-human sensory inputs, like hypothetical beings that perceive only electromagnetic waves.
>
> [...]
>
> ### Why These Signs Matter
> For LLMs to truly generate OOD text or knowledge, they would need to transcend the interpolation of training data distributions and demonstrate **abstract reasoning, novel synthesis, and extrapolation** in ways that cannot be attributed to memorization or in-distribution generalization. Detecting these signs would require rigorous testing and careful control to ensure no inadvertent overlaps with the training data.
>
> Such demonstrations would indicate that LLMs are not merely statistical pattern matchers but are capable of **autonomous abstraction and reasoning**, moving closer to general artificial intelligence.

Exciting times ahead.

