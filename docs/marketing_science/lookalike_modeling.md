
# Lookalike Modeling

This page summarizes practical concepts, methods, evaluation and implementation notes for lookalike (audience expansion) modeling used in marketing science.

## What is lookalike modeling?

Lookalike modeling finds new users who resemble a small high-value seed audience (e.g., converters, purchasers, loyal customers). The goal is to expand reach efficiently by prioritizing prospects with similar behaviors or attributes to the seed.

## Business use-cases

- New customer acquisition from small seed lists (email subscribers, high-LTV users).
- Campaign targeting and audience expansion for paid channels.
- Personalization and product recommendation seeding.
- Re-engagement by finding users similar to previously reactivated customers.

## Data requirements

- A labeled seed audience (positive examples) and a background population (unlabeled or negative examples).
- Feature set: demographics, engagement events, product interactions, recency/frequency/monetary features, behavioral embeddings.
- Linkage or deterministic identifiers if matching across systems; otherwise use probabilistic features.

## Typical pipeline

1. Define seed audience and business objective.
2. Assemble features for both seed and candidate populations.
3. Choose modeling approach (propensity scoring, similarity, embeddings).
4. Train model and score candidate pool.
5. Evaluate using historical holdout or A/B test.
6. Export top-K or thresholded lookalike audience for activation.

## Modeling approaches

- Propensity / classification: train a binary classifier to predict seed membership (logistic regression, XGBoost, LightGBM, neural nets). Score candidates and pick top percentiles.
- Similarity search: compute similarity between candidate vectors and the centroid/representative vectors of the seed (cosine similarity, Euclidean distance, nearest neighbors).
- Representation learning / embeddings: learn user/item embeddings from behavior (matrix factorization, neural embeddings) then use nearest neighbor search in embedding space.
- Hybrid: combine propensity scores with similarity or recency boosts to balance match quality and recency.

## Practical model choices

- Lightweight, interpretable: `logistic regression` with regularization for quick iteration and explainability.
- High-performance: `gradient boosting` (XGBoost/LightGBM/CatBoost) for non-linear feature interactions.
- Large-scale / representation: `approximate nearest neighbors` (FAISS, Annoy) on embeddings for very large candidate pools.

## Evaluation metrics

- Precision@K / Recall@K: fraction of true positives in top-K scored users.
- Lift (top decile): relative increase in conversion rate vs random sample.
- AUC / PR-AUC: holdout discrimination.
- Match rate / delivery rate: percent of exported audience that can be matched by ad platforms.
- Incremental uplift (best): measured by randomized holdout or A/B tests.

### Common evaluation functions (Python)

```python
import numpy as np

def precision_at_k(y_true, scores, k):
	idx = np.argsort(scores)[::-1][:k]
	return y_true[idx].sum() / float(k)

def lift_at_pct(y_true, scores, pct=0.1):
	n = int(len(scores) * pct)
	top_rate = y_true[np.argsort(scores)[::-1][:n]].mean()
	base_rate = y_true.mean()
	return top_rate / base_rate
```

## Implementation example (scikit-learn)

This simple example trains a propensity model to predict seed membership and exports the top lookalike candidates.

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import GradientBoostingClassifier
from sklearn.metrics import roc_auc_score

# df: users with features and a binary `is_seed` column
X = df.drop(columns=['user_id', 'is_seed'])
y = df['is_seed']

X_train, X_hold, y_train, y_hold = train_test_split(X, y, test_size=0.2, stratify=y)

model = GradientBoostingClassifier(n_estimators=200, learning_rate=0.05, max_depth=4)
model.fit(X_train, y_train)

scores = model.predict_proba(X_hold)[:,1]
print('AUC:', roc_auc_score(y_hold, scores))

# Score full candidate pool, then take top N
candidate_scores = model.predict_proba(candidate_df[feat_cols])[:,1]
candidate_df['score'] = candidate_scores
lookalikes = candidate_df.sort_values('score', ascending=False).head(100000)
```

## Deployment and scale

- Batch scoring: precompute scores daily and export top percentiles to DSPs. Use feature pipelines to ensure parity between train and scoring features.
- Real-time scoring: use a lightweight model (LR) served via API for on-the-fly decisions.
- For very large pools, compute embeddings and use ANN indexes (FAISS/Annoy/HNSW) to retrieve nearest neighbors efficiently.

## Matching, privacy & compliance

- Match rate: many ad platforms require hashed identifiers (email/phone). Always measure match rate early to estimate effective audience size.
- Privacy: avoid storing or exposing PII. Use hashed identifiers and follow platform policies and regulations (GDPR/CCPA).
- Bias & fairness: seed audiences may encode biases; evaluate demographic skews and consider constraints or re-weighting to avoid harmful outcomes.

## Pitfalls and best practices

- Small or noisy seed: use high-quality, well-defined seeds. Consider enrichment or enlarging the seed with near-seed examples.
- Data leakage: ensure temporal separation (use only data available at prediction time).
- Overfitting to platform-specific signals: prefer transferable features when expanding to multiple channels.
- Evaluate incrementally: run small A/B tests before full rollout.

## References & further reading

- Google Ads lookalike / Similar Audiences docs
- Facebook Lookalike Audiences documentation
- "Learning to Rank" and representation learning papers for embeddings
- FAISS: efficient similarity search library (GitHub)

--

This page is intentionally practical; if you want, I can add a runnable notebook example or a FAISS + embedding walkthrough next.

