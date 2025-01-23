---
date: '2025-01-24T08:32:18+11:00'
title: 'Stacking Ensemble With Dropout Regularization'
cover:
    image: /blog/pics/Stacking-Ensemble-With-Dropout-Regularization.webp
---

I was thinking about stacking ensembles (stacked generalization) in the sauna.

Stacked ensembles overfit, so we need to regularize.

Generally, we use cross-validation to ensure that the meta model is fit on out-of-fold predictions.

This is to avoid data leakage, but we could say it has a "regularizing" effect.

For reference, here's how that works via claude sonnet 3.5 (light editing from me):

---
> Let me explain how the meta-model in stacked generalization is fit using cross-validation:
>
> The key idea is to train the meta-model on out-of-fold predictions from the base models to avoid data leakage. Here's the process:
>
> 1. First, the training data is split into K folds (typically 5 or 10).
>
> 2. For each fold k:
>    - Train each base model on the data from all other K-1 folds
>    - Use these trained base models to make predictions on fold k
>    - Store these out-of-fold predictions along with the true target values
>
> 3. After doing this for all K folds, we have:
>    - A matrix of out-of-fold predictions from each base model for every training instance
>    - The corresponding true target values
>
> 4. The meta-model is then trained on this dataset where:
>    - Features are the out-of-fold predictions from each base model
>    - Target is the true target values
>
> 5. Finally, to make predictions on new data:
>    - Train each base model on the full training dataset
>    - Get their predictions on the new data
>    - Feed these predictions into the trained meta-model
>
> This cross-validation approach ensures the meta-model learns how to combine base model predictions without overfitting, since it never sees predictions from base models that were trained on the same data used to generate those predictions.

---

Me again.

I was thinking, can we use dropout when learning how to combine the predictions from lower level models in the meta model?

It probably makes most sense when the meta model is a linear model and we can zero out the predictions or coefficients randomly while training each model update.

Na, just gather out of fold predictions, and apply a dropout mask to the "dataset" prior to fitting the meta model.

If you recall dropout is a regularization method used in neural nets.

It involves zeroing out signals from a prior layer during forward and back propagation.

Here's a summary from claude:

---
> Dropout randomly deactivates neurons during training with probability p (typically 0.5 for hidden layers, 0.2 for input layer). > Key aspects:
>
> 1. In training:
>    - For each batch, randomly zero out different neurons
>    - Scale remaining activations by 1/(1-p) to maintain expected sum
>    - Backpropagate through non-dropped neurons only
>
> 2. In inference:
>    - Use all neurons (no dropout)
>    - No need to scale since using full network
>
> This prevents co-adaptation of neurons, reduces overfitting, and approximates model averaging of neural networks. The random dropping creates robust features useful in many contexts rather than features specific to training examples.

---

Me again.

Can we do the same kind of thing when learning how to combine predictions in a stacked ensemble?

And do we get benefits like model robustness and less reliance on specific models.

Reminds me of ablation studies on ensemble members.

Here's what claude thinks about the idea:

---
> Dropout in stacking's meta-model follows these steps:
>
> 1. During meta-model training:
>    - Apply dropout to base model predictions (features) with probability p
>    - Scale remaining predictions by 1/(1-p)
>    - Train meta-model on these masked features
>
> 2. During inference:
>    - Use all base model predictions without dropout
>    - Meta-model uses full feature set
>
> This prevents meta-model from overly relying on specific base models and helps learn robust combinations of predictions.

---

Okay, so thinking out loud here, I guess we could train the system to predict "1" for "no prediction" or "pass" on a classification task and then 1 for the first label, 2 for the second and on.

Or predict a probability (0-1) and 0.5 for a dropout "pass" prediction.

Then compare the result to the same setup with a linear model under L1, under L2, under L1+L2, and under no regularization.

Does it do better/worse/the same?

Might be fun!

Okay, so here's a tiny prototype of the idea (developed in with gpt4o, tweaked by me, then updated in gpto1):


```python
import numpy as np
import pandas as pd
from sklearn.datasets import make_classification
from sklearn.model_selection import train_test_split, cross_val_predict
from sklearn.metrics import accuracy_score
from sklearn.base import BaseEstimator, ClassifierMixin
from sklearn.neighbors import KNeighborsClassifier
from sklearn.svm import SVC
from sklearn.tree import DecisionTreeClassifier
from sklearn.linear_model import LogisticRegression

# -- 1. Create synthetic dataset ------------------------------------------------
X, y = make_classification(
    n_samples=1000,
    n_features=10,
    n_informative=8,
    n_redundant=2,
    random_state=42
)

X_train, X_test, y_train, y_test = train_test_split(
    X, y,
    test_size=0.2,
    random_state=42
)

# -- 2. Define simple base models -----------------------------------------------
base_models = [
    ("knn", KNeighborsClassifier(n_neighbors=5)),
    ("svc", SVC(probability=True, random_state=42)),
    ("dt", DecisionTreeClassifier(random_state=42))
]

# -- 3. Define the meta-model ---------------------------------------------------
meta_model = LogisticRegression(random_state=42)

# -- 4. Custom StackingWithDropout class ----------------------------------------
class StackingWithDropout(BaseEstimator, ClassifierMixin):
    """
    Manually stack base model predictions as features for a meta-model,
    with an added 'dropout' mechanism on the meta-features.
    """
    def __init__(self, base_models, meta_model, dropout_rate=0.2):
        self.base_models = base_models
        self.meta_model = meta_model
        self.dropout_rate = dropout_rate

    def fit(self, X, y):
        # Fit each base model on the entire training set
        # Collect out-of-fold predictions (cross_val_predict) for meta-features
        self.base_models_ = []
        self.meta_X_ = np.zeros((X.shape[0], len(self.base_models)))

        for i, (name, model) in enumerate(self.base_models):
            # Fit the model
            model.fit(X, y)
            self.base_models_.append((name, model))

            # For meta-features, use cross_val_predict with probabilities
            # (method="predict_proba"), then take the probability of the positive class
            preds = cross_val_predict(
                model, X, y, cv=5, method="predict_proba"
            )[:, 1]
            self.meta_X_[:, i] = preds

        # Apply dropout to meta-features
        meta_X_dropped = self._apply_dropout(self.meta_X_)

        # Now train meta-model on the dropout-augmented meta-features
        self.meta_model.fit(meta_X_dropped, y)
        return self

    def predict(self, X):
        # For prediction, get the base-model predictions
        meta_X_test = np.column_stack([
            model.predict_proba(X)[:, 1] for _, model in self.base_models_
        ])
        # Meta-model predicts the final output
        return self.meta_model.predict(meta_X_test)

    def _apply_dropout(self, meta_X):
        """
        Apply dropout to the meta-features:
          - With probability 'dropout_rate', replace each feature with 0.5.
          - With probability '1 - dropout_rate', leave it as is.
        """
        # Create a mask of True/False indicating which entries are "kept"
        mask = np.random.rand(*meta_X.shape) > self.dropout_rate
        # Where mask is False, assign 0.5
        meta_X_dropped = meta_X * mask + (1 - mask) * 0.5
        return meta_X_dropped

# -- 5. Compare models ----------------------------------------------------------
# Create two versions of stacking: one without dropout, one with dropout.
models = {
    "Stacking Without Dropout": StackingWithDropout(base_models, meta_model, dropout_rate=0.0),
    "Stacking With Dropout": StackingWithDropout(base_models, meta_model, dropout_rate=0.2),
    # For reference, train the meta-model directly on X (not recommended in practice)
    "MetaModel (Direct LR)": LogisticRegression(random_state=42),
    # For reference, each base model individually
    "KNN": base_models[0][1],
    "SVC": base_models[1][1],
    "DecisionTree": base_models[2][1]
}

results = {}

for name, model in models.items():
    # Fit the model
    model.fit(X_train, y_train)
    # Predict
    y_pred = model.predict(X_test)
    # Evaluate accuracy
    accuracy = accuracy_score(y_test, y_pred)
    results[name] = accuracy
    print(f"{name}: {accuracy:.4f}")

# -- 6. Display results ---------------------------------------------------------
results_df = pd.DataFrame(list(results.items()), columns=["Model", "Accuracy"])
results_df.sort_values(by="Accuracy", inplace=True, ascending=False)
print("\nResults:")
print(results_df.to_string(index=False))
```

Here's a sample output:

```text
Stacking Without Dropout: 0.9000
Stacking With Dropout: 0.9100
MetaModel (Direct LR): 0.6750
KNN: 0.8800
SVC: 0.9000
DecisionTree: 0.7300

Results:
                   Model  Accuracy
   Stacking With Dropout     0.910
Stacking Without Dropout     0.900
                     SVC     0.900
                     KNN     0.880
            DecisionTree     0.730
   MetaModel (Direct LR)     0.675
```

Looks like it is off to a good start!

Are there any papers on this kind of thing?

A quick search only turns up the application of stacking to MOOC dropout rates.

A search on perplexity finds papers on school dropout or the use of dropout in neural net ensembles.

Maybe this is all too obvious to warrant a paper.
