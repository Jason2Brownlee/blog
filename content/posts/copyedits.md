---
date: '2025-05-08T05:47:41+10:00'
title: 'Prompt for Copyediting'
---

I write a lot using sublime text.

It has only a very basic spellcheck and no grammar check.

Therefore, I use LLMs for basic copy editing.

I have [written about this before](/blog/posts/copyediting/).

A prompt I find useful recently is as follows:

```text
I will paste chapters from my novella in markdown/pandoc format.
Read them and report spelling errors and major grammatical errors.

- require UK/Australian English
- report any US spellings that must be changed
- report double words that are in error
- report missing words
- report spelling errors
- report grammatical errors that are no stylistic choices

Output errors in bullet point form with error and suggested change

I only want you to tell me about things I need to fix.
If there are no errors and correct spelling, say nothing.
Do not tell me about words that are spelled correctly.
```

I am able to paste 2 or 3 1k-2k chapters before it starts going off the rails. I then start a new chat and continue.

I typically use chatgpt, but grok3 is fine too.

No matter how many times I say, "don't tell me about correctly spelled words" it still does.

Oh well.



