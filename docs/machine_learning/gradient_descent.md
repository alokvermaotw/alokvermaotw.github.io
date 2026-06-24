- A _gradient_ is nothing but a derivative that defines the effects on outputs of the function with a little bit of variation in inputs. it is a slope of a curve at a given point in a specified direction.
- Gradient Descent (GD) is a widely used optimization algorithm in deep learning that is used to minimize the cost function of a neural network model during training.
- It works by iteratively adjusting the weights or parameters of the model in the direction of the negative gradient of the cost function until the minimum of the cost function is reached.
- **Gradient descent** (GD) is an iterative first-order optimization algorithm, used to find a local minimum/maximum of a given function.
Gradient Descent method’s steps are:
1. choose a starting point (initialization)
2. calculate gradient at this point
3. make a scaled step in the opposite direction to the gradient (objective: minimize)
4. repeat points 2 and 3 until one of the criteria is met:
	- maximum number of iterations reached
	- step size is smaller than the tolerance (due to scaling or a small gradient).
# Reference
- [Gradient Descent Algorithm — a deep dive | by Robert Kwiatkowski | Towards Data Science](https://towardsdatascience.com/gradient-descent-algorithm-a-deep-dive-cf04e8115f21)