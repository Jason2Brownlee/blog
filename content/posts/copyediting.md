---
date: '2025-03-21T15:00:19+11:00'
title: 'Copy-editing and Proofreading with LLMs'
---

I'm hunting for errors in my novella right now.

And finding a ton. Mostly inconsistencies and tiny grammar things.

This is something LLMs are great at. But there are some tricks.

I get better results if I give it 1/3 of the content at a time, rather than a single 30,000 word text file.

I also get better results if I use a reasoning model rather than a non-reasoning model. Specifically, gpto1, grok3+thinking, and R1+thinking.

Strange. I would have expected non-thinking models to do better, especially for simple copy-editing. Proofreading for inconsistencies do require reasoning, and that's fair enough.

Also, I found claude 3.7 to be TERRIBLE at this. Just so bad. Oh well. This again highlights the need to be using many models as part of your workflow, not one or two. An ensemble or council of AIs.

I's also important to specify exactly what you're looking for, e.g.:

* Spelling errors
* Grammar errors
* Typos
* Missing words
* Double words
* US vs British English

Sometimes I find it helps to add:

* Phrasing that is confusing to the reader.
* Obvious mistakes that make me look bad.

I also find it helpful to hunt for specific proofreading issues, e.g.:

* Read all footnotes that reference other chapters and confirm that the reference is correct (content appears in target chapter).
* Build a timeline and check that dates and times are consistent across all chapters.

And on.

Every single time I run one of these checked, I find stuff.

And not new stuff I've just added,  but clearly wrong stuff that I've had in there for days/weeks. Often things I've seen called out before and skipped over without checking, assuming the LLM was hallucinating or something. Nope. It's amazing. Human in the loop is the error :)

I also have to tell it specific things to ignore, e.g.:

- Style issues like capitalization, lots of full-caps bits for "yelling".
- My chosen mdash style, it really hates it.

Another tip is asking gpt4 (or similar) to build a solid prompt for this task. It can do it better than me.

