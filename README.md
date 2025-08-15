# Time Series Forecasting Analysis: Predicting American Retail Stock Prices

This project tests five different time series analysis models to forecast stock prices. I chose to focus on America's top retail companies because the retail sector serves as a critical economic indicator, reflecting consumer spending patterns, and broader market trends.
The five methods evaluated are:

- Manual ARIMA model
- ARIMA model with auto_arima from pmdarima
- Exponential smoothing
- Facebook Prophet
- Theta model

Every method was evaluated based on the root mean squared error (RMSE). I used RMSE because it penalizes large errors more than other popular metrics like Mean Absolute Error and Mean Absolute Percentage Error, making it ideal for identifying models that avoid significant forecasting mistakes in volatile stock price predictions.
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

The notebook `analysis.ipynb` demonstrates:

- Downloading historical stock price data for Walmart (WMT), Target (TGT), Costco (COST), Home Depot (HD), and Dollar General (DG)
- Monthly frequency conversion
- ARIMA modeling and forecasting
- Visualization of historical and predicted prices

The project uses open-source libraries and Yahoo! Finance data, making it easily adaptable to other stocks or time series.

## Features

- **Automatic Data Download**: Fetches price data for multiple tickers from Yahoo! Finance.
- **Visualization**: Plots historical monthly closing prices for all stocks.
- **Manual and Auto ARIMA**: Compares hand-tuned ARIMA with automated order selection using `pmdarima`.
- **Forecasting**: Produces 5-step forecasts for each stock.
- **Clear, Educational Code**: All steps are commented and easy to follow.

## Data

- **Source**: Yahoo! Finance via [`yfinance`](https://github.com/ranaroussi/yfinance)
- **Stocks Analyzed**:
  - Walmart (WMT)
  - Target (TGT)
  - Costco (COST)
  - Home Depot (HD)
  - Dollar General (DG)
- **Date Range**: 2015-01-01 to most recent available

## Requirements

Install all dependencies using:

```bash
pip install pandas yfinance matplotlib numpy statsmodels pmdarima
```

Or see the top of the notebook for individual commands.

## Usage

1. Clone this repository:
    ```bash
    git clone https://github.com/lhuang07425/time_series_analysis.git
    cd time_series_analysis
    ```

2. Open `analysis.ipynb` with Jupyter Notebook or JupyterLab:
    ```bash
    jupyter notebook analysis.ipynb
    ```

3. Run the notebook cells in order. The notebook will:
    - Download and preprocess data
    - Visualize historical trends
    - Fit ARIMA models and forecast future prices
    - Plot results

## Analysis Steps

The notebook is organized as follows:

1. **Install and Import Libraries**
2. **Data Download**: Fetch daily stock prices and convert to monthly frequency.
3. **Exploratory Visualization**: Plot all stocks on one chart.
4. **Manual ARIMA Modeling**: Fit a (1,1,1) ARIMA model as a baseline.
5. **Auto ARIMA Modeling**: Use `pmdarima` to select the best ARIMA order for each stock.
6. **Forecasting**: Forecast the next 5 months for each stock and plot results.
7. **Visualization**: Overlay historical and predicted prices for clear comparison.

## Results

- The notebook produces plots showing both historical and forecasted stock prices for each company.
- Example ARIMA and auto-ARIMA results are compared for each stock.
- The code can easily be adapted to new stocks or longer forecast horizons.

---

**Author:** [lhuang07425](https://github.com/lhuang07425)

For questions, open an issue or contact via GitHub.
````
