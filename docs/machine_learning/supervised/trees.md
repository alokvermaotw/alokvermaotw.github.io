# Decision Trees



# Random Forest
- Random forests are a type of ensemble method.
- Ensemble methods got their name because they consist of a collection of many simpler methods.
- Random forests consist of a collection of simpler decision trees. Every time you use a random forest regressor for prediction, the sklearn code creates many decision tree regressors. Each of the individual decision tree regressors is created with a different subset of the training data and a different subset of the training features. The final random forest prediction is the mean of the predictions made by each of the many individual decision trees.
- Choosing a random forest as your supervised learning method will probably increase your accuracy, but at the cost of interpretability and explainability. Every supervised  learning method has advantages and disadvantages, and choosing the right  trade-offs that are appropriate for your situation is important for any data scientist who wants to succeed at supervised learning.
- 