- The logistic function is an S-shaped curve (also known as a sigmoid curve) that, for a given set of input variables, produces an output variable between 0 and 1. Because the output variable is between 0 and 1 it can be used to represent a probability.
- Maximum Likelihood Estimation is used to fit this, which maximizes the likelihood a given logistic curve would output the observe data.
- Linear function in linear regression is log odd function in logistic regression.
- $$y = \frac{1.0}{1.0+e^-(\beta0+\beta1x)}$$

 ```python
def logistic_function(x, b0, b1): 
     p = 1.0 / (1.0 + math.exp(-(b0 + b1 * x))) 
     return p
```