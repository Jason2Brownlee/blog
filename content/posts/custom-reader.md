---
date: '2025-02-04T05:58:31+11:00'
title: 'Custom LLM-Based Reader'
---

We all should be making our custom readers.

I tripped over another [banger tweet](https://x.com/karpathy/status/1886200943471157418) by Andrej Karpathy:

> Last ~hour I built a custom LLM reader app so while I read Wealth of Nations I can ask questions about any paragraph. When you click a paragraph and "Ask" it calls an LLM, builds context window of what this is, copy pastes the full chapter, the paragraph, and the question. Works great.

Here's the tweet:

{{< twitter user="karpathy" id="1886200943471157418" >}}

Here's a larger version of the screenshot:

![](/blog/pics/custom-reader.jpg)

Like "paragraph comments", instead it's "paragraph chats" using the prior book/chapter as context.

Now consider this for anything you're currently reading through.

Fiction.

Non-Fiction.

Papers.

Blog posts.

News articles.

There are many times when I'm deep into a novel and I forget character and plot details. A quick chat would catch me up!

I'm sure there are mini apps that do this and browser plugins, but that's not the point.

We need to roll our own, to customize what to ask, how it is asked. We need to customize the context for our use case and knowledge base.

For example:

* If I'm re-reading a lovecraft short fiction, I may want to generate an image of a scene and iterate the style (e.g. [Cosmic Horror Story Art](https://github.com/Jason2Brownlee/CosmicHorrorStoryArt)).
* If I'm reading an algorithm description, I may want an implementation of the pseudocode in Python.
* If I'm reading a technical paper, I may want a simulation to prototype the idea.

I'm doing stuff like this now, but ad hoc, pasting in the context, phrasing the question, and iterating on the response.

If we put our own tools together (i.e. [vibe programming](https://x.com/karpathy/status/1886192184808149383)?), we can formalize and work on the "use case" itself rather than ad hoc'ing our way through each time. It's more active, and more interesting.

Perhaps an app wrapping for a book/text is simpler and more usable, as in the "[wealth of nations](https://en.wikipedia.org/wiki/The_Wealth_of_Nations)" example by Karpathy above.

We can imagine this for additional seminal texts, many of which that require translation from their original language or from old(er) English:

* [Philosophiæ Naturalis Principia Mathematica](https://en.wikipedia.org/wiki/Philosophi%C3%A6_Naturalis_Principia_Mathematica) (Newton)
* [De revolutionibus orbium coelestium](https://en.wikipedia.org/wiki/De_revolutionibus_orbium_coelestium) (Copernicus)
* [Dialogue Concerning the Two Chief World Systems](https://en.wikipedia.org/wiki/Dialogue_Concerning_the_Two_Chief_World_Systems) (Galileo)
* [On the Origin of Species](https://en.wikipedia.org/wiki/On_the_Origin_of_Species) (Darwin)

And modern texts that require a lot of re-reading and pondering:

* [Thinking, Fast and Slow](https://en.wikipedia.org/wiki/Thinking,_Fast_and_Slow) (Kahneman)
* [Antifragile](https://en.wikipedia.org/wiki/Antifragile_(book)) (Taleb)
* [The Beginning of Infinity](https://en.wikipedia.org/wiki/The_Beginning_of_Infinity) (Deutsch)
* [Gödel, Escher, Bach](https://en.wikipedia.org/wiki/G%C3%B6del,_Escher,_Bach) (Hofstadter)

And many others.

In fact, why would you bother to read these "hard" and hard-ish texts any other way?

I guess the form-factor.

Reading on the PC with a chat interface next to you for hours on end is harder than lazing in a comfy chair. Perhaps this is more for "studying" texts, in one hour blocks.

Hmmm.

If we're revisiting a text often (and I do, e.g. [especially business books](https://github.com/Jason2Brownlee/AuthoritySite)), even a simple "annotation" based mini-app for each book would be helpful. Pull out quotes and and capture main ideas.





