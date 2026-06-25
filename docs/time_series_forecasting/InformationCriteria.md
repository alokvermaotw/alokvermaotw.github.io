- Used to select the Optimal number of lags for the model. AIC, BIC and HQIC are used to compare different models and select the one which best fit the data.
# AIC
- Akaike Information Criterion
- Measure of the relative quality of a statistical model for a given data. it estimates the information lost when a model is used to represent the data.
- AIC = 2k - 2ln(L), where k is the number of parameters in the model and L is the Likelihood function.
- used to compare different models, lower is better while comparing
# BIC
- Bayesian Information Criterion
- Similar to AIC but places a higher penality on models with more parameters.
- BIC = ln(n)k - 2ln(L) where n is the sample size and L is the Likelihood function.
- used to compare different models, lower is better while comparing
# HQIC
- Hannan-Quinn Information Criterion
- Similar to AIC and BIC but places a higher penality on models with more parameters.
- HQIC = ln(ln(n))k - 2ln(L) where, 
- used to compare different models, lower is better while comparing


# Reference
- [How to Interpret ARIMA Results - Analyzing Alpha](https://analyzingalpha.com/interpret-arima-results)
- 