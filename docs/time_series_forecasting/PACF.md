- Partial autocorrelation can be imagined as the correlation between the series and its lag, after excluding the contributions from the intermediate lags.
- Conveys the pure correlation between a lag and the series.


# How to interpret PACF plot?
- 1. Look for significant spikes in the PACF plot. A spike at lag k indicates that the kth lag is significantly correlated with the current value of the time series.
-  Determine the order of the AR model based on the number of significant spikes in the PACF plot. For example, if there are significant spikes at lags 1, 2, and 3, then the order of the AR model would be 3.
- Use the Akaike Information Criterion (AIC) or Bayesian Information Criterion (BIC) to compare different models and select the one that best fits the data. The model with the lowest AIC or BIC value is considered the best fit.
