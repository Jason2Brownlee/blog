---
date: '2025-03-16T07:07:00+11:00'
title: 'LLM LaTeX-fu'
---

I build my books using [Pandoc](https://pandoc.org/) these days.

I used to use LaTeX directly, but Pandoc is better because I can write in markdown (clean+easy) then compile to epub and pdf for ebooks and paperbacks (pipeline).

Even though I'm writing in markdown, I can still use an include for custom LaTeX packages and configuration. This is very cool, because I can customize the paperback PDF to look really great.

The problem is, I forget all the cool LaTeX I'm supposed to use.

Thankfully, I can ask an LLM. Of course!

I've tried grok3, deepseek and gpt4.5 and get slightly different suggestions, but they all great.

I try prompts like

> "suggest pandoc LaTeX includes to make my pdf novel look more professional"

And:

> "suggest a tweak to the geometry that gives me more space for content but is still very professional looking"

I also tried:

> "my novel is like this and that, list fonts that best suit a novel of this type and look professional"

I tried a ton of fonts and finally got there. Yay! Fonts are the worst thing to pic, so much effect for such a small change. One suggestion was to have different parts of the book in different fonts (i.e. it's a found document type book), but I think that's a step too far.

My book has extensive footnotes, so I asked:

> "i have a lot of footnotes in my novel. what can i do to make my footnotes look really good and make best use of space, e.g. minimize footnotes spilling over multiple pages"

So good!

"**Professional**" is key here, because I self-publish and self-published books typically look bad.

Paperbacks built from LaTeX always look good, but they look like LaTeX books to those that know.

A few little tweaks and you can get something that looks very professional, and the LLMs know how.

No more stackoverflow or reading a ton package manuals. Thank god.




