- A deep learning algorithm based on [[Recurrent Neural Networks]]
- Designed specifically for time series forecasting
- works by learning a model based on all the time series data, instead of creating a separate model for each one.
- works better than creating a separate model for each time series.
- based on an autoregressive architecture, which means that it uses information from previous time steps to predict future values.
- It has two parts: an encoder network, which remembers what it has seen, and a decoder network, which predicts what will happen next.
- It learns a conditional distribution over the future values and uses a recursive approach to generate predictions for multiple time steps.
- So instead of simply predicting a point estimate, it samples values from the learned distribution and uses that as the prediction.
- For more detail and Difference between DeepAR and Prophet [look](https://forecastegy.com/posts/multiple-time-series-forecasting-with-deepar-in-python/). this site has reach collection of straight forward theoretical and practical concepts.






# Reference
- https://forecastegy.com/posts/multiple-time-series-forecasting-with-deepar-in-python/