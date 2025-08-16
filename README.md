# Time Series Forecasting Analysis: Predicting American Retail Stock Prices

This project tests five different time series analysis models to forecast stock prices. I chose to focus on America's top retail companies because the retail sector serves as a critical economic indicator, reflecting consumer spending patterns, and broader market trends.
The five methods evaluated are:

- Manual ARIMA model
- ARIMA model with auto_arima from pmdarima
- Exponential smoothing
- Facebook Prophet
- Theta model

Every method was evaluated based on the root mean squared error (RMSE). I used RMSE because it is easier to interpret then MSE, and also penalizes large errors more than other popular metrics like Mean Absolute Error and Mean Absolute Percentage Error, making it ideal for identifying models that avoid significant forecasting mistakes in volatile stock price predictions.
After determining the best model for forecasting stock prices, we found that the Auto ARIMA model achieved the lowest mean RMSE. The Auto ARIMA model outperformed the second-best model (seasonal auto ARIMA) by a statistically significant margin, with a p-value of 0.19639 from the t-test comparing their prediction accuracies.
We used the best-performing model to evaluate seasonal forecasting accuracy across three periods: January to May, March to July, and August to December. The January to May prediction period proved most accurate, though the difference compared to August to December predictions was not statistically significant (p-value = 0.43886).


## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Data](#data)
- [Requirements](#requirements)
- [Usage](#usage)
- [Analysis Steps](#analysis-steps)
- [Results](#results)

---

## Overview

This repository provides a complete workflow for monthly forecasting of stock prices for seven major American retailers: Walmart (WMT), Target (TGT), Costco (COST), Home Depot (HD), Dollar General (DG), Lowe’s (LOW), and TJX Companies (TJX). The core notebook (`analysis.ipynb`) demonstrates how to:

- Download historical price data from Yahoo! Finance using `yfinance`
- Convert daily prices to monthly frequency for analysis
- Compare multiple time series forecasting models, including both manual and automated ARIMA, Exponential Smoothing, Facebook Prophet, and Theta models
- Visualize historical trends and forecast results for each stock

All code is open-source, well-commented, and designed for easy adaptation to additional tickers or other time series problems.

## Features

- **End-to-End Pipeline**: From data download and preparation to analysis, modeling, and visualization
- **Multiple Retail Stocks**: Analyze and forecast prices for seven leading U.S. retailers
- **Model Comparison**: Evaluate manual ARIMA, Auto ARIMA, Exponential Smoothing, Prophet, and Theta
- **Educational Code**: Each step is explained and annotated for clarity
- **Adaptable**: Easily modify tickers, time ranges, or models for your own use case

## Data

- **Source**: Yahoo! Finance API via [`yfinance`](https://github.com/ranaroussi/yfinance)
- **Tickers**: WMT, TGT, COST, HD, DG, LOW, TJX
- **Period**: 2015-01-01 through the most recent available date

## Requirements

Install all necessary packages with:

```bash
pip install pandas yfinance matplotlib numpy statsmodels pmdarima
```

Or see the installation code at the top of the notebook for step-by-step commands.

## Usage

1. Clone the repository:
    ```bash
    git clone https://github.com/lhuang07425/time_series_analysis.git
    cd time_series_analysis
    ```

2. Open the notebook in Jupyter:
    ```bash
    jupyter notebook analysis.ipynb
    ```

3. Execute the cells in order. The notebook will:
    - Download and preprocess price data
    - Visualize historical prices for all stocks
    - Fit and compare time series models
    - Forecast future prices and plot results

## Analysis Steps

The notebook follows this logical structure:

1. **Install and Import Libraries**: Ensures all dependencies are available
2. **Data Download**: Retrieves daily price data and converts it to monthly frequency
3. **Visualization**: Plots monthly closing prices for all stocks to reveal trends
4. **Manual ARIMA Modeling**: Fits (1,1,1) ARIMA models to each stock as a baseline
5. **Auto ARIMA Modeling**: Uses `pmdarima` for automated order selection and fitting
6. **Additional Models**: Applies Exponential Smoothing, Prophet, and Theta models for comparison
7. **Forecasting and Plotting**: Forecasts next 5 months and overlays predictions on historical plots

## Results

- The notebook generates visualizations for each stock, showing both historical and forecasted prices
- RMSE is used to compare model performance, with Auto ARIMA generally providing the most accurate forecasts
- All code is designed for easy modification to new tickers, longer forecast horizons, or additional model types

---

**Author:** [lhuang07425](https://github.com/lhuang07425)

For questions, open an issue or contact via GitHub.