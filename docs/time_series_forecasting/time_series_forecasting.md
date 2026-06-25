- A time series is a sequence where a metric is recorded over regular time intervals.
- Depending on the frequency, a time series can be of yearly (ex: annual budget), quarterly (ex: expenses), monthly (ex: air traffic), weekly (ex: sales qty), daily (ex: weather), hourly (ex: stocks price), minutes (ex: inbound calls in a call canter) and even seconds wise (ex: web traffic).
- Forecasting is the step where you want to predict the future values the series is going to take.
- forecasting a time series can be broadly divided into two types.
	1. **Univariate Time Series Forecasting**:  If you use only the previous values of the time series to predict its future values.
	2. **Multi Variate Time Series Forecasting**: if you use predictors other than the series (a.k.a exogenous variables) to forecast

- Models that can be used for Time Series Forecasting:
	- [[ARIMA]]: If want to forecast a singe variable without considering external factors.
	- [[SARIMA]]: If want to forecast a singe variable with considering Seasonality and without considering external factors.
	- [[ARIMAX]]: If want to forecast a singe variable with considering external factors and without considering Seasonality.
	- [[SARIMAX]]: If want to forecast a singe variable with considering external factors and without considering Seasonality.

# Assumptions of Time Series
- Observations are not independent of each other.
- There is Trend, Seasonality and/or cyclic pattern in the data
# Assumptions of Time Series Forecasting
- Observations are not independent of each other.
- Stationarity
- Autocorrelation
- Absence of Seasonality and Trend.


# Stationary vs Non Stationary
- **stationary** time series is one whose statistical properties such as mean, variance, and covariance remain constant over time](https://otexts.com/fpp2/stationarity.html) [1](https://otexts.com/fpp2/stationarity.html). In other words, the properties of the time series do not depend on the time at which the series is observed. A stationary time series is easier to model and forecast than a non-stationary time series.

- **non-stationary** time series is one whose statistical properties change over time](https://otexts.com/fpp2/stationarity.html) [1](https://otexts.com/fpp2/stationarity.html). For example, a time series with a trend or seasonality is non-stationary because the trend and seasonality will affect the value of the time series at different times. Non-stationary time series are more difficult to model and forecast than stationary time series.