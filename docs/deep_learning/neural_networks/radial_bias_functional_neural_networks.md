- Type of [[Feedforward Neural Network]] that uses a set of radial basis functions to transforms its inputs and outputs
- composed of 3 layers: Input, hidden and output.
- Commonly  used for
	- pattern recognition
	- classification
	- Control tasks
	- Identify objects within an image.
- Works by first transforming the input data using a set of radial basis functions.  These functions calculate the distance between the input and a set of predefined centers in the hidden layer. The outputs from the hidden layer are then combined linearly to produce the final output. The weights of the connections between the hidden layer and the output layer are trained using a supervised learning algorithm, such as backpropagation.

RBF networks are often used for problems with large datasets because they can learn to generalize well and provide good predictions. They are also used for time-series analysis and prediction, as well as financial forecasting.

# Reference
- https://towardsdatascience.com/radial-basis-functions-neural-networks-all-we-need-to-know-9a88cc053448
- 