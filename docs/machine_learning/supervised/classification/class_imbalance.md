- happens when data is not equally represented across every outcome class,
- Class imbalance is still an open problem with no great solution. However, there are a few techniques that are people generally tries in industry that we can try.
- First, you can do obvious things like collect more data or try different models as well as use confusion matrices and ROC/AUC curves. All of this will help track poor predictions and proactively catch errors.
- Another common technique is to duplicate samples in the minority class until it is equally represented in the dataset.
- Pass the stratify option with the column containing the class values, and it will attempt to equally represent the data of each class.
```python

X, Y = ...
X_train, X_test, Y_train, Y_test = \
train_test_split(X, Y, test_size=.33, stratify=Y)
```

- There is also a family of algorithms called SMOTE, which generate synthetic samples of the minority class. What would be most ideal though is to tackle the problem in a way that uses anomaly-detection models, which are deliberately designed for seeking out a rare event. These seek outliers, however, and are not necessarily a classification since they are unsupervised algorithms.

# handing class imbalance techniques:- 
- Changing the performance matric
- Applying re-sampling techniques
- Generating synthetic data
- Changing selected algorithm

# My Thought
- Lets say we have 100 data points, 20 from class A and 20 from class B,
- Clearly it is an Class imbalance problem
- what if we take that 20 class of a and get 20 class from b of only those samples which are matching in most of the characteristic and create 4 model and then finally take the average of each model and get the final model as output.