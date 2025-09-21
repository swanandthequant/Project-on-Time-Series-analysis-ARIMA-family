# Bank Nifty Time Series Analysis
## Methodology

The project was done on Bank Nifty index data with the main goal to check how different time series models work on financial data. The steps I followed were more or less like this:

## Data Collection & Cleaning

1.Imported Bank Nifty historical data.

2.Did some cleaning, handling missing values, making sure the index was proper time series format.

3.Some small preprocessing like checking stationarity with ADF test, and differencing when required.

## Exploratory Analysis

1.Plotted the data to see the trends and seasonality.

2.Used ACF and PACF plots to figure out p and q values for AR/MA parts.

3.Tried to see if there is seasonality that could be captured by SARMA/SARMAX.

## Model Building

1.Started with ARMA as baseline.

2.Then moved to SARMA for seasonal patterns.

3.Added ARMAX to see effect of external/exogenous variables (though honestly not much impact since external features were limited).

4.Finally tried SARMAX which is like combining both worlds.

## Evaluation

1.Checked the models with AIC, BIC, RMSE.

2.Also looked at residual plots to see if they were white noise or still patterns left.

3.Compared forecasting accuracy between the models.

## Visualization

1.Plotted predicted vs actual values.

2.Seasonal decomposition plots to understand trend and seasonality better.

## My Insights

1.ARMA worked okay but it was too simple for the data. The residuals showed patterns left.

2.SARMA was more promising since Bank Nifty clearly has seasonality (monthly/quarterly cycles). It captured that better.

3.ARMAX didn’t add much improvement, maybe because the external variables were not strong enough or maybe I didn’t choose right ones.

4.SARMAX gave the best performance overall (lower AIC/BIC and better residual behaviour).

5.Still, financial time series are tricky – models are never perfect. Prediction errors were significant during high volatility periods.

### Main takeaway: adding seasonality really matters for Bank Nifty type of index, but adding exogenous regressors only helps if they are meaningful (like macroeconomic indicators, not random features).

Another point is that statistical models are good for short-term forecasting but may struggle with long-term horizons in markets.

## Limitations

1.Didn’t test with very large range of external features, so ARMAX/SARMAX results might not be optimal.

2.More tuning of hyperparameters could improve forecasts.

3.Dataset itself could have been expanded with more years or minute-level data for deeper insights.

## Note: This analysis is for academic/learning purpose only. Please don’t take this as investment advice.