---
date: '2025-02-14T05:58:14+11:00'
title: 'Technical Analysis in Other Fields'
---

I was reading a [book about the Occult + Nazi's](https://www.goodreads.com/book/show/35238287-hitler-s-monsters) the other day and there was a mention of _technical analysis_ for astrology.

As an aside, Germany went bananas for the occult in the early part of the century, then later the Nazi's, because it was already in the air, e.g. [Occultism in Nazism](https://en.wikipedia.org/wiki/Occultism_in_Nazism)

Anyway, my thought:

> Huh? Technical analysis for a field other than finance... that makes sense I guess.

I filed it away to ponder...now.

Recall, [technical analysis](https://en.wikipedia.org/wiki/Technical_analysis) is the idea of looking for patterns in data, so much so that you may be "discovering" trends that are artifacts of random noise and not predictive.

From our friend DeepSeek:

> Technical analysis is a method used to evaluate and predict the future price movements of securities, such as stocks, currencies, or commodities, by analyzing statistical trends gathered from trading activity, such as price movement, volume, and historical data. Unlike fundamental analysis, which focuses on a company's financial health and intrinsic value, technical analysis relies on chart patterns, technical indicators, and other tools to identify trends, support and resistance levels, and potential entry and exit points for trades. Practitioners believe that all relevant information is already reflected in the price, and by studying past market behavior, they can make informed decisions about future price movements. Common techniques include the use of moving averages, relative strength index (RSI), Fibonacci retracements, and candlestick patterns. While technical analysis is widely used by traders, its effectiveness is debated, as it is based on the assumption that historical patterns will repeat, which may not always hold true in dynamic markets.

It's mostly bunk.

At least, that's what I remember from reading "[A Random Walk Down Wall Street](https://www.goodreads.com/book/show/40242274-a-random-walk-down-wall-street)".

That is what has kept me away from doing ML + finance anytime someone asked (and they asked daily for years).

Anyway, I had not considered "technical analysis" in other fields.

It makes sense.

Especially in fields that don't have strong scientific backing, either because they are pseudoscience, or because doing science is really hard/a new field and methods are not well established.

Technical analysis in occult fields makes sense, e.g. astrology.

But now it makes me worry.

Technical analysis sounds EXACTLY like what ~~most~~ many "data scientists" are doing.

**Is data science technical analysis for business?** Probably.

I asked gpt4o, and as always, he's too agreeable by default:

> Yes, I completely agree with your broader definition of technical analysis as a statistical, pattern-seeking approach rather than a first-principles approach. Your framing highlights both the power and the risk of technical analysis—extracting useful signals from data but sometimes mistaking randomness for meaningful patterns.

And:

> Many business decisions today rely on predictive models and pattern recognition from large datasets. Like in finance, the risk is in mistaking spurious correlations for meaningful trends. Businesses use machine learning models, A/B testing, and anomaly detection without always knowing the first-principles reasons behind their findings.

But yes, it appears data science looks like data science for business.

Especially if you ignore (or don't have access to) domain knowledge.

> Yes, data science in business often functions like technical analysis:
>
> * It finds correlations and patterns in data to optimize operations, predict customer behavior, and improve decision-making.
> * Many business analytics models are based on statistical correlations rather than deep causal understanding.
> * Machine learning models, which power much of modern data science, are excellent at finding patterns but can suffer from overfitting—the business equivalent of mistaking noise for a signal in financial markets.

What about other fields that look like "technical analysis"?

* Sports Analytics
* Epidemiology
* Political Forecasting
* Criminal Profiling
* Behavioral Economics

Oh yeah. Agreed.

And pseudoscience + "technical analysis" methods?

> * **Astrology**: It identifies patterns in planetary movements and correlates them with human events or personality traits.
> * **Numerology**: Looks for patterns in numbers (e.g., birthdates, names) and assigns meaning to them.
> * **Paranormal & Ghost Hunting**: Uses sensors, recordings, and temperature fluctuations to "detect" ghosts based on patterns.
> * **Cryptozoology**: Identifies supposed patterns in reported sightings, footprints, and blurry images.
> * **Alternative Medicine**: Relies on anecdotal "trends" in patient outcomes without rigorous testing.
> ...

And on... I got many examples from gpt4o.

You can see so many "fields and people fall into this trap. You're gathering data and looking scientific, but you're not doing science.

Okay, so how do we tell the difference between good statistical methodology and "technical analysis" (e.g. "pattern seeking")?

My first thought is "falsification", e.g. a good scientific hypothesis that we can seek to refute with evidence.

I had a long chat about this with our bro 4o.

Here's a nice summary table contrasting the "good science" from "pattern seeking" technical analysis:

| **Criteria**               | **Good Science** | **Technical Analysis (in the bad sense)** |
|-----------------------------|-----------------|------------------------------------|
| **Causal Explanation**       | Seeks mechanisms | Assumes correlation = causation |
| **Falsifiability**          | Can be disproven | Often vague, unfalsifiable |
| **Replication**             | Independently verified | Rarely tested outside original context |
| **Statistics**              | Proper controls, significance testing | Cherry-picked data, p-hacking |
| **Confounding Factors**      | Controlled for | Ignored or unknown |
| **Theory-Based?**           | Grounded in theory | Purely pattern-based |
| **Transparency**            | Open methods, peer review | Secretive, proprietary methods |
| **Time Horizon**            | Long-term repeatability | Short-term patterns that fail over time |
| **Predictive Power**        | Can forecast future events | Only "explains" past data |
| **Scientific Skepticism**    | Welcomes scrutiny | Defends patterns at all costs |


And this summary:

> The key difference is that **good science aims to uncover objective truths**, while "technical analysis" in its broadest form often **relies on pattern recognition without understanding why**. If a method cannot be tested, repeated, and explained, it's more likely to fall into the realm of unreliable technical analysis or even pseudoscience.

Very cool.

I like "_Purely pattern-based_" and "_correlation = causation_".

Lots of this going on in "data science" and "machine learning" :)

I recall a clever friend, Gerry, in our research group circa 2004 pointing out all the time that "_just because your model gets high 90s accuracy for a breast cancer or diabetes dataset doesn't mean it knows anything about those diseases_."

Right on!






