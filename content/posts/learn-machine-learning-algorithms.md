---
date: '2025-01-29T08:02:51+11:00'
title: 'How to Learn Machine Learning Algorithms (for Programmers)'
---

I've written a ton of tutorials and books to help developers learn machine learning algorithms over the years.

It's not my area any longer, but if asked, my suggestion for a programmer (that **learns via programming**) is to code machine learning algorithms from scratch.

Is this you? It is me. It's how I learn best.

Here, I really mean that we learn best by:

1. reading about thing
2. writing code for the thing
3. running the thing
4. it doesn't work (it never works first go)
5. iterate until the implementation works (and you really-actually-deeply learn the thing)

This is how _we programmers_ learned a ton of algorithms and data structures in our CS or SWE degree, or whatever.

As pedagogy, it's so much more effective than passively reading or playing with existing implementations of algorithms.

Notice, youtube edutainment does not feature here at all. It's a terrible way to (deeply) learn a technical topic.

So, how can we learn machine learning algorithms by coding them from scratch?

The zeroth order would be:

* You could "implement" algorithms from scratch in a spreadsheet (e.g. google sheets).

The language of machine learning is Python.

So, use python:

* You could code algorithms from scratch in (vanilla) Python.
* You could code algorithms from scratch using the SciPy stack (e.g. NumPy).

Do this. It's great.

There's another step.

The preferred "platform" for using/evaluating machine learning algorithms (not neural nets) is scikit-learn.

Therefore:

* Code algorithms from scratch in scikit-learn.

**If you only pick one approach, do this**.

If I was to write yet another book on how to code ML algorithms from scratch, I'd write it along these lines.

Why?

Because you can focus on the algorithm and plug it into the sklearn framework and evaluate it along side all the other algorithms.

If you implement the simple `fit()` and `predict()` API methods, your implementation immediately becomes a "first class citizen" of the framework and you get all the model evals, metrics, datasets, etc. for free.

For example, here's a simple "dummy regressor" using the sklearn API:

```python
from sklearn.base import BaseEstimator, RegressorMixin
import numpy as np

class MeanRegressor(BaseEstimator, RegressorMixin):
    def __init__(self):
        self.mean_ = None

    def fit(self, X, y):
        y = np.asarray(y)  # Ensure y is a numpy array
        self.mean_ = np.mean(y)
        return self

    def predict(self, X):
        if self.mean_ is None:
            raise ValueError("This MeanRegressor instance is not fitted yet. Call 'fit'.")
        n_samples = X.shape[0]
        return np.full(n_samples, self.mean_)

# Example usage
if __name__ == "__main__":
    # Sample data
    X_train = np.array([[1], [2], [3]])
    y_train = np.array([4, 5, 6])

    # Initialize and train the model
    model = MeanRegressor()
    model.fit(X_train, y_train)

    # Predict
    X_test = np.array([[10], [20], [30]])
    y_pred = model.predict(X_test)

    print("Predictions:", y_pred)
```

Running the example gives:

```text
Predictions: [5. 5. 5.]
```

A good place to start is the official docs, here:

* [Developing scikit-learn estimators](https://scikit-learn.org/dev/developers/develop.html)

You can also implement your own hyperparameter search algorithms, your own resampling methods, your own metrics, and more.

Keep your implemenations super-simple.

They are for you. You're not coding enterprise-grade ML algorithms here.

You're coding as a learning tool, the code will ultimately be disposable.

Don't over think it.

Don't go full-on with docs, and params, and specific API magic.

Grab a great machine learning textbook that describes algorithms well, like "[An Introduction to Statistical Learning](https://www.statlearning.com/)" and get started coding algorithms from scratch in sklearn.

