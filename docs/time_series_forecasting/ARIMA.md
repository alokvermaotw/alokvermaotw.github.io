- Autoregressive Integrated Moving Average
- A forecasting algorithm based on the idea that the information in the past values of the time series can alone be used to predict the future values.
- In other words  ‘explains’ a given time series based on its own past values. that is, its own lags and the lagged forecast errors, so that equation can be used to forecast future values.
- first introduced by George Box and Jenkins, in 1970 in a book titled "Time series analysis Forecasting and Control", it is aka box jenkins apprach.
- Here the parametric terms are
	- Autoregressive -> p : (means: it is a [[Linear Regression]] Model that uses its own lags as predictors, we can find out the required number of AR terms by inspecting the Partial Autocorrelation (PACF) plot.)
	- Moving Averages -> q : (means: refers to the number of lagged forecast errors that should go into the ARIMA Model.)
	- Integrated -> d (it is the process of making Non stationary Time Series to Stationary Time Series, here d is the number of differencing the original series has to undergo in order to get the stationary.  we do differencing by subtracting the previous value from the current value.)

- Seasonality Pattern: some kind of patterns repeating at some intervals.
- If Seasonality present in the data it cannot be modeled using the [[ARIMA]] for that case we need to use [[SARIMA]]


Reference
1. [1-Understanding ARIMA - Machine Learning Plus](https://www.machinelearningplus.com/arima/understanding-arima-model/)
2. [ARIMA Model - Complete Guide to Time Series Forecasting in Python | ML+ (machinelearningplus.com)](https://www.machinelearningplus.com/time-series/arima-model-time-series-forecasting-python/)
3. [How to Interpret ARIMA Results - Analyzing Alpha](https://analyzingalpha.com/interpret-arima-results)
4. [What Is an ARIMAX Model? | 365 Data Science](https://365datascience.com/tutorials/python-tutorials/arimax/)
5. 
6. 