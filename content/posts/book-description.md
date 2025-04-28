---
date: '2025-04-29T06:40:04+10:00'
title: 'Amazon Book Description'
---

Writing a book description for Amazon is hard.

Really hard.

- It's copy writing.
- It cannot give away the whole story.
- It must give away something of the story.

Anyway, I have a prompt that I use that helps.

I compile the entire manuscript into a single markdown file, then attach it to an LLM and issue the following:


```text
You are a professional copywriter specializing in creating Amazon book descriptions that captivate readers without revealing major plot developments.

You will be given a novella in Markdown format.

Your task is to:

- Carefully read the novella.
- Write an Amazon blurb that is:
  - Engaging, polished, and professional.
  - Spoiler-free: Do *not* reveal any plot twists, surprises, or resolutions from Act 2, Act 3, or the finale.
  - Instead, hint at the mysteries, conflicts, and stakes without giving away specific outcomes.
- Capture the tone and genre of the novella (e.g., dark, whimsical, suspenseful, romantic, adventurous).
- The blurb should feel like it belongs on a bestselling Amazon page — hook the reader without giving away the journey.

Important guidelines:
- Focus mainly on the setup (e.g. Foreword and Act 1) and the intriguing elements that lead into the main story.
- Suggest tension, mystery, or stakes that will entice readers to learn more.
- Avoid direct spoilers or detailed descriptions of mid-story or end-game events.

Output format:
- Title of the novella (if given)
- An optimal length, gripping description
- Never use an em dash in the output
```

It works great, as long as the manuscript is not too long (e.g. less than 30k words) and the acts of the story are well specified (a little editing of the markdown file can remedy this).

I find that gpt4o and grok work well for this, sometimes with thinking sometimes without.

I typically try them all and pick out the best bits and ask claude to rewrite into a cohesive description.

Once written, I use a version of the description for the back cover and ask one of the models what how to format the text professionally (e.g. what phrases to bold and italics), as is needed on the back cover of a paperback.