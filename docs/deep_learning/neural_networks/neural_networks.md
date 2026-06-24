# Neural Networks
- a neural network is a multilayered regression containing layers of weights, biases, and nonlinear functions that reside between input variables and output variables.
- Provides the solution but explanation???
- when all you have is a hammer, everything starts to look like a nail
- Each node essentially is a linear function with slopes Wi and intercepts Bi being multiplied and summed with input variables Xi. There is a weight Wi between each input node and hidden node, and another set of weights between each hidden node and output node. Each hidden and output node gets an additional bias Bi added.
![[neural_network.png]]
- _In a nutshell, this is a regression just like linear or logistic regression, but with many more parameters to solve for. The weight and bias values are analogous to the m and b, or β1 and β0, parameters in a linear regression. We do use stochastic gradient descent and minimize loss just like linear regression, but we need an additional tool called backpropagation to untangle the weight Wi and bias Bi values and calculate their partial derivatives using the chain rule. We will get to that later in this chapter, but for now let’s assume we have the weight and bias values optimized. We need to talk about activation functions first._
- Layers of Neural Networks
	- Input Layer 
	- Hidden Layer
	- Output Layer
		- The output layer has an important job: it takes the piles of math from the hidden layers of the neural network and turns them into an interpretable result, such as presenting classification predictions. it uses [[Activation Function]] in between.

- when we pass a node’s weighted, biased, and summed value through an activation function, we now call that an _activated output_, meaning it has been filtered through the activation function.

- in literature defined as 'The action of widely spreading and promoting an idea'

- Chain Rule ???
# Forward Propagation


# Backward Propagation

- Useful when we need to deal with semi or un structured data.
- Variants of neural networks
	1. [[Feedforward Neural Network]]
	2. [[Perceptron]]
	3. [[Multilayer Perceptron]]
	5. [[Recurrent Neural Networks]]
	6. [[Long Short Term Memory]]
	7. [[Radial Basis Functional Neural Network]]
	8. [[Convolutional Neural Network]]
	9. [[Autoencoder Neural Networks]]
	10. [[Sequence to Sequence Models]]
	11. [[Modular Neural Network]]

# Reference:
- [10 Types of Neural Networks, Explained - HackerRank Blog](https://www.hackerrank.com/blog/types-of-neural-networks-explained/)