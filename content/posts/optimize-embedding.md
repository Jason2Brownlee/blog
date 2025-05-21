---
date: '2025-05-22T09:16:52+10:00'
title: 'Latent space optimization?'
---

I was randomly thinking about embeddings this morning.

I was thinking how they are fantastic at creating a continuous representation space from discrete data, e.g. words, category labels, etc.

I was then thinking it might be fun to use the embedding as a representation for an optimization process, like a genetic algorithm. Or any optimization algorithm.

The algorithm would sample the embedding space and drawn vectors would have to be evaluated using a simulator or objective function or whatever, depending on the domain.

The benefit is compression, you can fit a lot of data in an embedding and most importantly, small changes in the latent space represent small changes in the output space.

I'm sure the clever kids have explored this, but it might be fun to do some experiments with this.

What is this exactly?

- Directed sampling latent space?
- Latent space optimization?
- Embedding optimization?

I must have read about this before and it's popped back into my head...

Domains where this might be cool would be cases where we have a ton of cheap/free data, the data is discrete (or can be made so naturally), and where traditional representations are challenging.

Obvious cases include sampling variable-length strings like plain text, program code, etc.

But what else?

- molecule design
- material design
- music design
- game level design
- behaviour/strategy design
- layout design
- floor plans

Okay, anything.

Maybe I'll code up something fun sometime soon...