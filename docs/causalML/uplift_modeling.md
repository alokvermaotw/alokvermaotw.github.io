# Uplift Modeling
- Enables the identification of customers who are most likely to respond positively to treatments, thereby improving the marketing ROI.
- The goal is to select the right users for targeting
- i.e.: Uplift tree / Uplift random forest

## Methods for Uplift modeling
### [Meta Learners](https://alokvermaotw.github.io/causalML/meta_learners/)
- Predicts the outcome with treatment and the outcome without treatment seperately, and then calculate the uplift.
- ie T-Learner (Two modal approach)
### [Decision Tree](https://alokvermaotw.github.io/machine_learning/supervised/classification/decision_tree_classifier.md) Based Methods
- Directly estimates the uplift
- ie: [Uplift Tree](), [Uplift Random Forest]()
- Some algorithms supports multiple treatment groups (5% coupons, 10% coupons, 15% coupons)
- Feature Importance
- While uplift modeling can be implimented with `Meta Learners`, `Decision Tree` based method is a common approach.

## *Traditional Decision Trees* to *Uplift Tree*
| Traditional Decision Tree | Uplift Tree |
| --- | --- |
|Will the customer make a purchase? (**Prediction**) | Who should we give coupons to? (**Causality**)
| Just splits in `Yes` or `No` | After spliting in `Yes` and `No` It splits futher `Yes` to `Treated` and `Not Treated` same for `No`.
