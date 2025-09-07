## Bank Nifty Time Series Analysis

This repo is my small project where I try to understand how Bank Nifty behaves over time.
I have done three things here – built Auto Regression (AR) models, Moving Average (MA) models, and also played with White Noise & Random Walk to see how they look.

## 1. Data Preparation

I used Yahoo Finance data for ^NSEBANK and ^NSEI from 2010 till mid-2025.

Removed missing values (just forward filled them, maybe not the best way but it works).

Focused only on Bank Nifty closing prices and made it into one clean column called Market_value.

Split data 80-20 into train and test.

## 2. First Look at the Data

Plotted ACF and PACF to see any patterns.

Ran Dickey Fuller test to check if the data is stationary (spoiler: prices are not).

Made a small function to do Likelihood Ratio test so I can compare models easily.

## 3. AR Model Work

Tried AR(1), AR(2), AR(3).

Looked at p-values and LLR results – AR(1) was good enough for using (as LLR for others were way more than our significance level 5%)

Residuals were checked and looked okay (mean close to 0, no big spikes).

## 4. MA Model Work

Tried MA(1) up to MA(8).

LLR tests showed MA(6) is working best, so I used that one.

Residuals again looked fine and didn’t show big autocorrelation.

## 5. White Noise & Random Walk

Generated white noise just to see what pure randomness looks like.

Created random walk and compared – you can really see how it drifts compared to white noise.

Plotted ACF and PACF, random walk clearly not stationary (as expected!).

## 6. What I Learned

AR(1) can capture some short term memory in Bank Nifty prices, but not everything.

MA(6) gave slightly better residuals so maybe price shocks have a bit longer effect.

White noise and random walk are super helpful to visualize before fitting any model.

Still a lot more to try like ARMA, ARIMA, maybe even GARCH later.
