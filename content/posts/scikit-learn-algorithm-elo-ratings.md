---
date: '2025-01-10'
title: 'Scikit-Learn Algorithm Elo Ratings'
cover:
    image: "/blog/pics/regression_ratings.png"
---

I've been reading up on [AutoGluon](https://auto.gluon.ai/) on and off over the last few weeks.

It's amazing!

I highly recommend the podcast episode [AutoGluon: The Story](https://automlpodcast.com/episode/autogluon-the-story) with Nick Erickson from 2023.

Anyway, one cool thing Nick touched on in his AutoML 2024 presentation was Elo ratings for AutoGluon and a suite of other AutoML frameworks.

Here's a still from the presentation that captured my imagination:

![Elo Ratings for Tabular ML Methods](/blog/pics/Screenshot-Elo-Ratings-for-Tabular-ML-Methods.png)

Watch the whole presentation:

* [[AUTOML24] AutoGluon: Towards No-Code Automated Machine Learning](https://www.youtube.com/watch?v=SwPq9qjaN2Q)

I love this idea.

I know a little about chess rating algorithms, from [some work back in 2010 for an early kaggle competition](https://github.com/Jason2Brownlee/ChessML).

Also, like most people, I've seen the [LLM Chatbot Arena](https://lmarena.ai/?leaderboard) that also uses Elo ratings.

This got me thinking.

So I sat down with gpt4o and we designed a simple arena for classification and regression algorithms in scikit-learn.

One arena for each problem type, standard datasets provided by the library and all algorithms for each problem type.

We then coded up each arena in a way that results are stored to an sqlite database and re-running each arena refines the Elo scores for each algorithm.

It's just a prototype, but you can see the code and results here:

* [Scikit-Learn Arena](https://github.com/Jason2Brownlee/SKLearnArena): Elo Ratings for classification and regression algorithms in scikit-learn.

Here's a cool ranking plot of Elo ratings for sklearn regression algorithms:

![Elo ratings scikit-learn regression algorithms](/blog/pics/regression_ratings.png)

