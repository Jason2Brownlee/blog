---
date: '2025-01-25T10:27:21+11:00'
title: 'The Bitter Lesson Leads To Evolutionary Computation'
---

I saw a note about [the bitter lesson](http://www.incompleteideas.net/IncIdeas/BitterLesson.html) go by and I left a comment.

It's an idea I've had a for a long time but not really said out loud.

Recall the bitter lesson (via claude):

> The Bitter Lesson, articulated by Rich Sutton in 2019, argues that in artificial intelligence research, methods that leverage computation and large amounts of data have historically outperformed approaches based on human knowledge and hand-crafted rules. The "bitter" part is that our human intuitions about how to solve problems often turn out to be less effective than simple methods that scale well with computing power. This has been demonstrated repeatedly in areas like computer chess, speech recognition, and machine translation, where brute-force computational approaches ultimately surpassed carefully designed human-engineered solutions.

Some (obvious?) implications, from gpt4o:

> * Focus on general learning approaches that can leverage massive data and computation.
> * Recognize that manual encoding of knowledge is less scalable and often suboptimal.
> * Accept that progress may sometimes feel unintuitive or less satisfying because it minimizes the role of human-crafted insight.


My thought is that a/the ultimate implication of the bitter lesson is that we will eventually fall back to stochastic optimization as our general problem solver.

E.g. optimize or evolve artifacts on demand.

I think once we get a few more orders of magnitude of computation (more for less), we will see the rise of [evolutionary computation](https://en.wikipedia.org/wiki/Evolutionary_computation) (in some form) as general problem solver.

The implication here is that neural nets/LLMs is not the end.

In fact, I believe neural nets/stochastic gradient descent are also a type of hand-crafted solution and that the more general solution (evolutionary search) may or will produce better systems of problem solving.

Not that big a leap, really. Obvious even?

Here's a paste of [my comment](https://www.reddit.com/r/deeplearning/comments/1i8qaud/comment/m902a65/):

> I think about "the bitter lesson" a lot.
>
> We have been throwing off the yoke of hand-crafted algorithms for a decade and a half now, in favor of optimizing end-to-end systems, typically neural net systems.
>
> I think the "neural net" (as we currently know it) is probably a hand crafted artifact (perhaps the circuits, perhaps the training algorithm).
>
> I think we have one more level to discard and go full "evolutionary search" on hard problems. Inefficient. Dumb. Slow. Powerful.
>
> Keep that computation coming.

So what does gpt4o think (snippets from his response)?

> * Evolutionary computation is a highly general optimization method inspired by natural selection. It doesn’t rely on handcrafted domain-specific knowledge but instead explores a wide solution space using stochastic processes like mutation, crossover, and selection.
> * This aligns with the Bitter Lesson's emphasis on general methods outperforming specialized ones as scale and compute increase.
> * Evolutionary algorithms, while computationally expensive, can scale effectively with the availability of more computational resources. As computation becomes cheaper and more powerful, the inefficiencies of evolutionary methods may be less problematic compared to their ability to discover novel, high-performing solutions.
> * In the future, with abundant computational power, evolutionary methods might even discover architectures, algorithms, or designs that outperform those crafted by humans.

Noodling on this now... I don't think this is a possibility, I'm certain a version of this will come about.

Out LLM friend also pointed out trends along this path already, including AutoML.

Nod. Good point.