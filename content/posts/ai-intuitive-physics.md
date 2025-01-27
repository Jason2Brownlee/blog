---
date: '2025-01-28T06:31:52+11:00'
title: 'AI Intuitive Physics'
---

In the last two episodes of "[the cognitive revolution](https://www.cognitiverevolution.ai/)" podcast, the host (Nathan Labenz) has mentioned AI's developing an intuition for the physics of a domain.

Specifically:

* [Material Progress: Developing AI's Scientific Intuition, with Orbital Materials' Jonathan & Tim](https://www.youtube.com/watch?v=eVlXEJhCRvo)
* [Emergency Pod: Reinforcement Learning Works! Reflecting on Chinese Models DeepSeek-R1 and Kimi k1.5](https://www.youtube.com/watch?v=MbX9J1Tt_I0&ab_channel=CognitiveRevolution%22HowAIChangesEverything%22)

By "physics", he means the actual __rules__ that limit physical domains, but we can generalize and say any domain.

In fact, the phrase "AI's Intuitive Physics" is used in a thumbnail on a video right now:

![ai intuitive-physics](/blog/pics/ais-intuitive-physics.webp)

There's no transcript of the interview I can find, here's my manual transcription (from closed captions) that gives a flavor of this part of the discussion.

A monologue from Nathan on this topic of "intuitive physics" at the top of the episode:

> ...neural networks seem to have the ability to develop a sort of **intuitive physics** in virtually any problem space. Just as humans can catch a ball without explicitly calculating its trajectory, these AI systems are developing efficient shortcuts for predicting complex physical phenomena. Whether that's material properties, protein folding and interactions, weather forecasts, single cell transcriptomes, or even the evolution of human brain states. For me, this is the clearest reason to believe that superhuman intelligence is not just possible, but increasingly likely...

Right on.

More from one of the guests later on when Nathan brings up "intuitive physics" in the interview:

> ...my theory is that it's something to do with dimensionality reduction, right, that often you don't need to treat every single part of a system and so in our case we're kind of this is called course-graining in physics and statistical mechanics there's great theories of it...

Nod, agreed.

And:

> Finding efficient ways of keeping track of the important information and losing the unimportant information is just a central problem in a lot of physical modeling. And I think AI, machine learning algorithms are just very very good at doing that.

And:

> ...so it is quite incredible and I think that **intuitive physics** explanation is [a] really nice way of thinking about what's going on, because it's just in the same way that you get extraordinary sports people who can score incredible goals and do incredible feats but know any maths. That's exactly what these AIs are doing when they're doing these simulations...

And from the solo episode:

> ...it seems that they [neural network models] can develop a sort of **intuitive physics** in those different problem spaces that humans are nor capable of because our biological neural networks are just not that flexible. Vert few people can develop a deep intuition for how to optimize some of these, you know, far out problems...

Yep.

Let me untangle some thoughts.

Nathan touches on Wolfram's idea of [computational irreducible complexity](https://en.wikipedia.org/wiki/Computational_irreducibility) in physical systems and that neural nets are finding short cuts (like we humans do, I might add, when we come up with laws of motion, etc.).

> Computational irreducibility suggests certain computational processes cannot be simplified such that the only way to determine the outcome of such a process is to go through each step of its computation.

Yep, we need shortcuts in these domains.

A guest touches on [dimensionality reduction](https://en.wikipedia.org/wiki/Dimensionality_reduction), and it is a piece of this.

> Working in high-dimensional spaces can be undesirable for many reasons; raw data are often sparse as a consequence of the curse of dimensionality, and analyzing the data is usually computationally intractable

There's too much data and we need to efficiently pay attention to the aspects that matter, that have leverage, even if that involves a transform of the data as presented.

But there's an intuiting the "rules" and "reasoning from these rules in the domain" piece. And the reasoning appears emergent - which is nice. What do we call all that?

I'm also reminded of [grokking](https://en.wikipedia.org/wiki/Grokking_(machine_learning)).

> ...grokking, or delayed generalization, is a transition to generalization that occurs many training iterations after the interpolation threshold, after many iterations of seemingly little progress, as opposed to the usual process where generalization occurs slowly and progressively once the interpolation threshold has been reached

But really, we're just talking about generalization, and who cares how/when this happens in practice during training. What matters is that the models are usefully generalizing in complex/physical domains and "discovering" the "intuitive physics" as a forced problem-solving strategy to minimize loss.

Anyway, I think this is no small point.

The field is focused on inference-time compute in order to "do reasoning", but can we force a model to learn and acquire the intuitive physics of system 2 thinking/reasoning directly (whatever that means)?


