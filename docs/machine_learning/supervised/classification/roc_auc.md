- When we are evaluating different machine learning configurations, we may end up with dozens, hundreds, or thousands of confusion matrices. These can be tedious to review, so we can summarize all of them with a receiver operator characteristic (ROC) curve
- allows us to see each testing instance and find an agreeable balance between true positives and false positives.
- We can also compare different machine learning models by creating separate ROC curves for each. For example, if our top curve represents a logistic regression and the bottom curve represents a decision tree (a machine learning technique we did not cover in this book), we can see the performance of them side by side. The area under the curve (AUC) is a good metric for choosing which model to use. Since the top curve (logistic regression) has a greater area, this suggests it is a superior model.
- To use the AUC as a scoring metric, change the scoring parameter in the scikit-learn API to use roc_auc as shown for a cross-validation in Example 6-18. Example 6-18. Using the AUC as the scikit-learn parameter
```python

# put Scikit_learn model here
results = cross_val_score(model, X, Y, cv=kfold, scoring='roc_auc')
print("AUC: %.3f (%.3f)" % (results.mean(), results.std()))
# AUC: 0.791 (0.051)

```
