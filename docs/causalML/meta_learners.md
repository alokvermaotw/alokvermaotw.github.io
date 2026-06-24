# Meta Learners
- The goal is to measure treatment effect.
- i.e.: S-learner, T-learner, DML etc

## Types of Meta Learners

| Learner | Approach | Reference | Training Speed (Relative to S Learner) | Defination |
| --- | --- | --- | --- | --- |
| S-Learner | Single-Model Approach | Kunzel et al. 2019 | 1x | Uses a single modal for training and prediction of both outcome with treatment and without treatment.
| T-Learner | Two-Model Approach | Kunzel et al. 2019 | 2x | Uses seperate modal for treatment and control groups.
| X-Learner | Cross-Fitting Approach | Kunzel et al. 2019 | 5x | 
| DR-Learner | Doubly Roboust | Kennedy et al. 2020 | 13x |
| DML | Double Machine Learning | Chernozhukov, Victor, et al. 2019 | 27x |

## How to select appropriate Meta Learner
- Step 1. : Start with simple methods to get a baseline.
- Step 2. : Compare other methods by measuring accuracy Such as MAPE, RMSE and performing refutation for robustness.