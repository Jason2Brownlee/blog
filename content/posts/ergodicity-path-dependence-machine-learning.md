---
date: '2025-01-25T08:28:01+11:00'
title: 'Ergodicity and Path Dependence in Machine Learning'
---

I was thinking about ergodicity yesterday in the context of machine learning.

Specifically the path-dependency of training the "best" model and our typical solution to this challenge to train a monte carlo ensemble of final models (e.g. same learning algorithm + varied random seeds, same training data) and combine their predictions.

Could we do better? Are we really stuck and is this really the best way out?

My introduction to [ergodicity](https://en.wikipedia.org/wiki/Ergodicity) came initial from Taleb's books. I think it was [Antifragile](https://www.goodreads.com/book/show/13530973-antifragile) that dug into (the related idea) of [Jensen's inequality](https://en.wikipedia.org/wiki/Jensen%27s_inequality) for the payoff in games, and his book [Skin in the Game](https://www.goodreads.com/book/show/36064445-skin-in-the-game) that dug into ergodicity in games with ruin.

Great series of books, need to add to the re-read stack for 2025.

Anyway, from gpt4o:

> In simple terms, ergodicity refers to whether the long-term behavior of a system for an individual is the same as the behavior of the system across an ensemble of individuals or trials at a single point in time.
>
> * **Ergodic systems**: The average outcome over time for a single individual is the same as the average outcome across many individuals (or trials) at one point in time.
> * **Non-ergodic systems**: The time average for a single individual differs from the ensemble average. This distinction is critical because real-world systems often exhibit non-ergodicity.

Taleb points out this matters a lot in systems/games where one of the sample points in the system is ruin.

Taleb shared this idea on Medium (cira 2017) in a post titled "[The Logic of Risk Taking](https://medium.com/incerto/the-logic-of-risk-taking-107bf41029d3)".

Here's a snippet with a scenario that makes the point:

> Consider the following thought experiment.
>
> First case, one hundred persons go to a Casino, to gamble a certain set amount each and have complimentary gin and tonic –as shown in the cartoon in Figure x. Some may lose, some may win, and we can infer at the end of the day what the “edge” is, that is, calculate the returns simply by counting the money left with the people who return. We can thus figure out if the casino is properly pricing the odds. Now assume that gambler number 28 goes bust. Will gambler number 29 be affected? No.
>
> You can safely calculate, from your sample, that about 1% of the gamblers will go bust. And if you keep playing and playing, you will be expected have about the same ratio, 1% of gamblers over that time window.
>
> Now compare to the second case in the thought experiment. One person, your cousin Theodorus Ibn Warqa, goes to the Casino a hundred days in a row, starting with a set amount. On day 28 cousin Theodorus Ibn Warqa is bust. Will there be day 29? No. He has hit an uncle point; there is no game no more.
>
> No matter how good he is or how alert your cousin Theodorus Ibn Warqa can be, you can safely calculate that he has a 100% probability of eventually going bust.
>
> The probabilities of success from the collection of people does not apply to cousin Theodorus Ibn Warqa.

The contrast is between ensemble probability and time probability.

Again from gpt4o:

> **Ensemble Probability vs. Time Probability**
>
> * **Ensemble Probability**: Aggregates the outcomes of many parallel instances of a system at a single point in time. It assumes independence and large numbers.
> * **Time Probability**: Tracks the outcome of one instance of the system over time, accounting for path dependence and compounding effects.
>
> **Key Insights:**
> * **Survivorship Bias**: Ensemble averages can be misleading because they don't account for the paths of those who experienced ruin and are no longer part of the sample.
> * **Risk Management**: Non-ergodic systems require cautious behavior to avoid ruin, even if the ensemble expectation seems favorable.
> * **Multiplicative Effects**: In real life, outcomes often compound multiplicatively (e.g., wealth growth, health), meaning that a single catastrophic event has an outsized impact.

And:

> One of Taleb's major insights is that many real-world scenarios involve games or decisions where ruin (complete loss, bankruptcy, or death) is possible. This creates path dependency: outcomes in a non-ergodic system depend on the specific path taken over time.
>
> In games with ruin, you cannot simply average out probabilities or outcomes because if ruin occurs, the game ends for you.
The ensemble probability (averaging across many individuals or trials) might suggest a positive outcome, but for a single participant over time, a catastrophic event (ruin) can lead to a permanent loss, invalidating the time average.

You can't expect the average return because along the way one of your samples may cause you to zero-out of the game completely.

Good stuff.

Anyway, I was thinking about a lighter version of this, in predictive modeling.

In general, we evaluate and choose a model based on "Ensemble Probability". We use statistical methods to estimate the average expected behavior of the system.

A single final model trained on all available data has [path dependence](https://en.wikipedia.org/wiki/Path_dependence). We don't know how it will perform exactly, only how models like this trained on data like that are expected to perform on average.

From [Wikipedia](https://en.wikipedia.org/wiki/Path_dependence):

> Path dependence is a concept in the social sciences, referring to processes where past events or decisions constrain later events or decisions. It can be used to refer to outcomes at a single point in time or to long-run equilibria of a process.

We can mitigate this risk by training an ensemble of many copies of the same model with different random seeds on the same training data (or subsamples there of) and average their predictions. This moves us closer to the average expected performance of the chosen system.

Checking in with gpt4o, we get a good summary:

> Ergodicity in the Context of ML
> To connect to ergodicity, let’s reframe the problem in terms of ensemble probability and time probability:
>
> 1. **Ensemble Probability**:
>    * If you train multiple models independently with different random seeds and observe their predictions at a given point in time, you’re analyzing the ensemble distribution of model performance.
>    * Ensembling predictions from multiple models is analogous to exploiting this ensemble distribution to improve generalization and robustness.
> 2. **Time Probability**:
>    * Imagine following the performance of a single model as it trains (or fine-tunes) across epochs. This gives the time evolution of the model's predictive power.
>    * Depending on the algorithm, the path to convergence can vary due to randomness in optimization, but this process is often path-dependent, especially in non-convex optimization spaces like those of deep learning.

Digging deeper, I guess gpt4o agrees that we are finding a workaround.

We find an "**ergodic proxy**" or "**ergodic approximation**" with our ensemble of final models.

> Training many models and ensembling predictions essentially creates an ergodic approximation. While individual training runs may vary significantly, the ensemble smooths out variability, leading to more consistent performance.

And in non-ergodic systems/games, we seek to reduce variance:

> In non-ergodic systems, reducing variance is often more valuable than optimizing for the best possible outcome. This aligns with the use of ensembles, cross-validation, and other techniques that stabilize outcomes in ML.

Okay, so no deep insights, just another way to look at the same old stuff.

One insight I guess.

Perhaps we can use a validation set to monitor the path dependence of a given training run an choose a model that is expected to do well/better compared to the expected value/average.

As long as the validation set is fantastic (robustly representative of the domain).

I checked in with gpt4o and it agreeded, but it also suggested to perhaps try [random seed hacking](https://github.com/Jason2Brownlee/MachineLearningMischief/blob/main/examples/seed_hacking.md) (!) when training final models.

> If computational resources permit, train multiple models with different random seeds and evaluate each on the validation set:
> * Rank models based on their validation performance.
> * Select the best-performing model from this ensemble for deployment.
>
> Path Dependence Insights: This approach explicitly leverages path dependence, recognizing that some training runs may "luckily" find better local optima.

Damn!

Also, does the idea of an "ergodic approximation" help in other non-ergodic domains that we often treat/evaluate as ergodic?

I guess, it's the same benefit that angel/vc investors get by investing across a portfolio of companies. Sucks for any individual company, given they are likely to "fail" (by some definition of fail), but it's great for the operator at the next level up that can ~~average~~ [argmax](https://en.wikipedia.org/wiki/Arg_max) across the portfolio.

Checking in with gpt4o, yep, we are doing this all over the place (of course we are).

* Financial Investments and Risk Management
* Insurance and Actuarial Science
* Medicine and Healthcare
* Engineering and Systems Design
* Education and Skill Development
* Climate Change and Environmental Policy
* Game Design and Artificial Intelligence
* Social Policy and Economics
* Sports and Team Performance
* Product Development and Innovation
* And on...

Some of these really matter for the individual participating in the non-ergodic game, like medicine :

> The Problem: Medical outcomes are non-ergodic for individuals: a single adverse event (e.g., a fatal side effect or a missed diagnosis) can have permanent consequences, even if the average population outcome is good.
>
> Ergodic Proxy/Approximation:
> * Clinical Trials and Evidence-Based Medicine: Randomized controlled trials (RCTs) are an ensemble-level approximation, helping predict how treatments perform across populations.
> * Personalized Medicine: By stratifying populations into risk groups, healthcare can simulate ensemble-level outcomes within subgroups to make better time-average predictions for individuals.

The objective for the future of all fields is bespoke everything. Tailored everything. One-on-one everything.

Monitoring (validation sets?) for the ~~training~~ execution run and early stopping for all non-ergodic things we do. We do this, I guess. Maybe agents/LLMs/AI-magic can help in domains were we don't or don't do it well?

Off the rails now... moving on.

