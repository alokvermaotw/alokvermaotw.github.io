- When training a machine learning model, the model can be easily overfitted or under fitted. To avoid this, we use regularization in machine learning to properly fit the model to our test set. 
- Regularization techniques help reduce the possibility of overfitting and help us obtain an optimal model.
# Types of Regularization
- _L1_: Lasso Regularization --> Lasso [[Regression]]
	- _LASSO_: Least Absolute Shrinkage and Selection Operator
	- Adds the absolute value of magnitude of the coefficient as the penalty term to the [[Loss function]] 
	- Also helps achieve feature selection by penalizing the weights to approximately equal to zero if that feature doesn't serve any purpose in the model.
	- ||w||1=( |w1|+|w2|+ . . . + |wn|
	- with sklearn package it asks for two parameter alpha and tol
- _L2_: Ridge Regularization --> Ridge Regression
	- Adds the squared magnitude of the coefficient as the penalty term to the [[Loss function]]
	-  ||w||2=( |w1|2+|w2|2+ . . . + |wn|2 )1/2 where w is the weight
	- with sklearn package it asks for one parameter alpha
- _L1 and L2_: Elastic Net Regularization
	- Implies that we add the absolute norm of the weights as well as the squared measure of the weights
	- With the help of an extra hyperparameter this controls the ratio of the L1 and L2 regularization.

