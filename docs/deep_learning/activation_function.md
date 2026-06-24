- A non linear function that transforms or compresses the weighted and summed values in a node, helping the neural network separate the data effectively so it can be classified.
- If you do not have the activation functions, your hidden layers will not be productive and will perform no better than a linear regression.
- The activation function could have strengthened, weakened, or left the signal as is. This is where the brain and synapse metaphor for neural networks comes from.

| Name               | Typical Layer Used | Description                                   | Notes                                                                                                                     |
| ------------------ | ------------------ | --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Linear             | Output             | Leaves Values as is                           | Not Commonly used                                                                                                         |
| Logistic           | Output             | S-shaped sigmoid curve                        | Compresses values between 0 and 1, often assist binary classification                                                     |
| Tangent Hyperbolic | Hidden             | tanh, S-shaped sigmoid curve between -1 and 1 | Assist in 'centering' data by bringing mean to 0                                                                          |
| ReLU               | Hidden             | Turns Negative values to 0                    | Popular activation function popular than sigmoid and tanh, mitigates vanishing gradient problem and computationally cheap |
| Leaky ReLU         | Hidden             | Multiplies values by 0.01                     | Controversial variant of ReLU that marginalizes rather than eliminates negative values.                                   |
| Softmax            | Output             | Ensures all output nodes add up 1.0           | Useful for multiplication classification and rescaling outputs so they add upto 1.0                                       |
- This is not a comprehensive list of activation functions, and in theory any function
could be an activation function in a neural network.

- If you are unsure what activations to use, current best practices gravitate toward ReLU for middle layers and logistic (sigmoid) for output layer. If you have multiple classifications in the output, use softmax for the output layer.

# ReLU
- Relu is short for Rectified Linear Unit,
- `Turn negative values into zero`
- The ReLU activation function will zero out any negative outputs from the hidden nodes. If the weights, biases, and inputs multiply and sum to a negative number, it will be converted to 0. Otherwise the output is left alone.
- `relu = Max(0, x)`
- ReLU is popular because of its mitigation of the [Vanishing gradient problem], which occurs when the partial derivative slopes so small they prematurely approach 0 and bring training to a screeching halt.

# Logistic Activation Function
- aka Sigmoid curve
- The logistic (or sigmoid) function demonstrates that logistic regression is acting as a layer in our neural network. The output node weights, biases, and sums each of the incoming values from the hidden layer. After that, it passes the resulting value through the logistic function so it outputs a number between 0 and 1.
- `logistic = 1 / (1 + exp(-x))`