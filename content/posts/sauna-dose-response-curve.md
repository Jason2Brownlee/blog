---
date: '2025-03-05T06:19:47+11:00'
title: 'Sauna Dose-Response Curve'
---

I was thinking about how sauna is supposed to reduce all cause morality, according to some random paper.

I asked GPT DeepResearch to find the paper and summarize the data.

We found:

* [Association between sauna bathing and fatal cardiovascular and all-cause mortality events](https://pubmed.ncbi.nlm.nih.gov/25705824/) (2015)

(I didn't read the paper, the numbers below could be hallucinated, I'm just having fun this morning)

Summarized by DeepResearch:

>**Data Summary:**
>
>1. **Frequency of Sauna Use:**
>   - 1 session per week
>   - 2-3 sessions per week
>   - 4-7 sessions per week
>
>   The study found that compared to men who had one sauna session per week, those who had 2-3 sessions per week had a 24% lower risk of all-cause mortality, and those with 4-7 sessions per week had a 40% lower risk.
>
> 2. **Duration of Sauna Sessions:**
>    - Less than 11 minutes
>    - 11-19 minutes
>    - More than 19 minutes
>
>    Regarding session duration, the study reported that compared to sessions lasting less than 11 minutes, those lasting 11-19 minutes did not show a significant reduction in all-cause mortality. However, sessions longer than 19 minutes were associated with a 52% lower risk of sudden cardiac death.

Good.

I then asked GPT4o to create some Python and plot the dose-response curves for the two datasets:

![sauna-dose-response-sessions](/blog/pics/sauna-dose-response-sessions.png)

![sauna-dose-response-duration](/blog/pics/sauna-dose-response-duration.png)

Nice, now, let's create a model and see what's up.

## Model of Sauna Sessions Per Week

First, let's look at dose-response for sessions per week.

![sauna-dose-response-sessions-model](/blog/pics/sauna-dose-response-sessions-model.png)

Table:


| Sauna Sessions per Week | Hazard Ratio | Relative Decrease in Mortality (%) |
|-------------------------|--------------|------------------------------------|
| 1                       | 1.000        | 0.00%                             |
| 2                       | 0.820        | 17.97%                            |
| 3                       | 0.714        | 28.64%                            |
| 4                       | 0.650        | 34.98%                            |
| 5                       | 0.613        | 38.74%                            |
| 6                       | 0.590        | 41.00%                            |
| 7                       | 0.575        | 42.49%                            |
| 8                       | 0.564        | 43.59%                            |
| 9                       | 0.557        | 44.28%                            |
| 10                      | 0.552        | 44.78%                            |


Not that exciting, 5 sessions seems to be a point of diminishing returns, at least from this data.

## Model of Sauna Minutes Per Session

Now, let's look at minutes per session.

It first tried to fit a quadratic, which was really wrong.

It then used a log-fit. Better I guess, but not awesome. I'm just hacking around and this is fine for now.

![sauna-dose-response-minutes-model](/blog/pics/sauna-dose-response-minutes-model.png)

Table:

| Minutes in Sauna | Hazard Ratio | Relative Decrease in Mortality (%) |
|-----------------|--------------|------------------------------------|
| 1               | 1.065        | 0.00%                             |
| 2               | 1.060        | 0.52%                             |
| 3               | 1.054        | 1.06%                             |
| 4               | 1.048        | 1.64%                             |
| 5               | 1.041        | 2.25%                             |
| 6               | 1.034        | 2.91%                             |
| 7               | 1.026        | 3.63%                             |
| 8               | 1.017        | 4.39%                             |
| 9               | 1.008        | 5.21%                             |
| 10              | 0.999        | 6.00%                             |
| 11              | 0.989        | 6.84%                             |
| 12              | 0.978        | 7.74%                             |
| 13              | 0.967        | 8.69%                             |
| 14              | 0.955        | 9.69%                             |
| 15              | 0.942        | 10.65%                            |
| 16              | 0.929        | 11.64%                            |
| 17              | 0.915        | 12.71%                            |
| 18              | 0.900        | 13.84%                            |
| 19              | 0.885        | 15.06%                            |
| 20              | 0.869        | 16.35%                            |
| 21              | 0.852        | 17.72%                            |
| 22              | 0.835        | 19.17%                            |
| 23              | 0.817        | 20.70%                            |
| 24              | 0.798        | 22.32%                            |
| 25              | 0.779        | 24.03%                            |
| 26              | 0.759        | 25.82%                            |
| 27              | 0.738        | 27.69%                            |
| 28              | 0.717        | 29.65%                            |
| 29              | 0.695        | 31.70%                            |
| 30              | 0.672        | 33.83%                            |


If you stay in the sauna for a long time you will live forever.

Na, 20 mins is fine I guess.

What we need is better data! Controlled experiments, put humans in cages for their entire lives, randomize everything else and dose with specific sauna sessions/minutes. Super easy, right :)