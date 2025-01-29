---
date: '2025-01-30T09:39:06+11:00'
title: 'Embedding-Based Recommendations'
---

I was thinking about LLM as a recommender system.

I [wrote about this](/blog/posts/llm-based-recommendation-engine/) the other day, how they can give a different type of recommendation.

> It occurs to me that we can use LLMs to give better recommendations.
> I want this for books.

But, LLM recommendations are different how?

That's what I was thinking about.

So, the most basic recommendations are:

- Other books by the author
- Other books in genre

The most popular [recommender systems](https://en.wikipedia.org/wiki/Recommender_system) for the last 15+ years are [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering).

- Users that read this book also read... (e.g. goodreads)

or:

- Customers who bought this book also bought... (e.g. amazon)

Most machine learning/data science people code up one of these with a kNN at some point. With good data, a collaborative filtering model is not challenging.

Anyway, LLM recommendations are more like the former and less like the latter.

They are in latent space or embedding space.

Let's call them **embedding-based recommendations**.

They are more semantic, e.g. meaning based.

If I say I like Dan Simmons' "[Hyperion](https://www.goodreads.com/book/show/77566.Hyperion)" and ask for recommendations, from gpt4o I get:


> If you loved *Hyperion* by Dan Simmons, you're likely looking for books with epic scope, literary depth, intricate > world-building, and philosophical themes. Here are some recommendations that capture similar elements:
>
> ### **Space Opera with Literary & Philosophical Depth**
> 1. **The Book of the New Sun** – Gene Wolfe
>    - A deeply poetic and layered series that follows Severian, a torturer exiled from his guild, in a world that feels both > futuristic and medieval.
>
> 2. **The Revelation Space series** – Alastair Reynolds
>    - A mix of hard sci-fi and gothic horror with vast interstellar civilizations, mysterious artifacts, and a sense of inevitable > decay.
>
> 3. **Ilium & Olympos** – Dan Simmons
>    - If you loved *Hyperion*, this duology by Simmons blends Greek mythology with space opera and quantum physics.
>
> 4. **Anathem** – Neal Stephenson
>    - A heady, philosophical sci-fi novel about a cloistered society of scholar-monks grappling with cosmic mysteries.
>
> 5. **The Culture series** – Iain M. Banks (*Start with Consider Phlebas or The Player of Games*)
>    - A vast and imaginative series exploring post-scarcity civilizations, AI Minds, and the moral dilemmas of utopia.
>
> ### **Classic Sci-Fi With Similar Themes**
> 6. **Dune** – Frank Herbert
>    - A masterpiece of political intrigue, mysticism, and epic storytelling set on the desert planet Arrakis.
>
> 7. **The Left Hand of Darkness** – Ursula K. Le Guin
>    - A literary sci-fi classic exploring gender, identity, and political intrigue on an alien world.
>
> 8. **The Stars My Destination** – Alfred Bester
>    - A revenge-driven space odyssey with cyberpunk vibes and a powerful antihero.
>
> 9. **Gateway** – Frederik Pohl
>    - A mix of psychological depth and hard sci-fi about a man haunted by his past as he seeks answers in ancient alien starships.
>
> 10. **The Manifold Trilogy (Manifold: Time, Space, Origin)** – Stephen Baxter
>    - Deeply ambitious books exploring the nature of intelligence, the Fermi paradox, and the fate of the universe.
>
> ### **More Experimental and Unique Sci-Fi**
> 11. **Blindness** – José Saramago
>    - Not sci-fi in the traditional sense, but a haunting allegory about human nature in extreme conditions, reminiscent of > Simmons' thematic depth.
>
> 12. **Blindsight** – Peter Watts
>    - A mind-bending first-contact novel exploring consciousness and the limits of human perception.
>
> 13. **Permutation City** – Greg Egan
>    - A fascinating take on simulated realities, consciousness, and the nature of existence.
>
> 14. **The Quantum Thief** – Hannu Rajaniemi
>    - A dazzling post-cyberpunk novel with a poetic, fragmented storytelling style.
>
> 15. **House of Suns** – Alastair Reynolds
>    - A standalone novel about post-human descendants traveling the stars across millions of years.
>
> Would you like recommendations based on a specific aspect of *Hyperion*—such as its structure, poetic language, or philosophical themes?


What's it doing?

I'm getting recommendations on many specific aspects of "hyperion", like:

* Space Opera with Literary & Philosophical Depth
* Classic Sci-Fi With Similar Themes
* More Experimental and Unique Sci-Fi

And it's _so very useful_.

And the other classical and collaborative filtering methods ~~will not~~ may not get there. At least, not this way.

And, we can do more, like ask for more or different books related to specific aspects of the plot, setting, characters, author, genre, and on.

This can be codified into a prompt:

1. Consider and analyze the themes of the book.
2. List the 3 most predominate themes of the book from the analysis.
3. List 5 most relevant books for each of the 3 predominate themes.

Then:

1. Repeat for plot/setting/characters/author/etc.
2. Strip duplicates and books already read
3. Give the logline for each book and a line on how its related/interesting/recommended
4. Link on amazon/goodreads

Then repeat for tv/movies/podcasts/all media consumed...

As a consumer, this has not been unlocked for me (fully) yet.

I have to do it manually, and so most often won't.

No research project needed, we have all the parts. Hook up the openai API to the goodreads API and send a daily email with the best recommendations. In fact, a zapier automation could probably get this done :)

I'm sure people are working on this.

Maybe me and my gpt4o-bro can code up a prototype on a rainy afternoon soon.

