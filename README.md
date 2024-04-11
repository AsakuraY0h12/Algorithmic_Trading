# Algorithmic_Trading
This repository contains Python code implementing a comprehensive algorithmic trading strategy that uses machine learning and quantitative analysis techniques. The strategy focuses on the S&P 500 companies, leveraging various financial indicators and factors to inform trading decisions.

## Algorithmic Trading Using Machine Learning and Quantitative Strategies

#### Overview
The code is structured to cover the entire process of algorithmic trading strategy development, from data acquisition to portfolio optimization and backtesting. Here's a breakdown of the process:

#### 1. Data Acquisition
S&P 500 Companies: Scrapes Wikipedia to fetch the current list of S&P 500 companies, adjusting ticker symbols for Yahoo Finance compatibility.
Historical Data Download: Uses yfinance to download 8 years of daily stock price data for the fetched companies.
#### 2. Data Preparation
Cleaning: Reshapes the dataset, adjusting column names and indexing.
Feature Engineering: Adds calculated features such as Garman-Klass volatility, RSI, Bollinger Bands, ATR, and MACD.
#### 3. Analysis and Transformation
Monthly Aggregation: Converts daily data to month-end frequency to streamline the analysis.
Liquidity Filtering: Applies a 5-year rolling average of dollar volume to filter out the top 150 stocks based on liquidity.
#### 4. Returns Calculation and Outlier Handling
Computes historical returns for various periods and applies outlier treatment to normalize the returns distribution.
#### 5. Fama-French Factors Integration
Incorporates the Fama-French five-factor model, estimating exposure to common risk factors using linear regression.
Filters stocks to ensure sufficient historical data and calculates rolling factor betas.
#### 6. Clustering
Uses K-Means clustering based on predefined RSI values, hypothesizing that certain clusters indicate stocks likely to outperform.
#### 7. Portfolio Optimization
Employs the PyPortfolioOpt library to maximize the Sharpe ratio, defining optimal weights for selected stocks.
Implements fallback to equal weighting in case of optimization failure.
#### 8. Strategy Implementation and Backtesting
Downloads recent prices for shortlisted stocks, calculates daily returns, and optimizes portfolio weights monthly.
Aggregates strategy returns over time for performance evaluation.
#### 9. Error Handling
Includes try-except blocks to manage errors gracefully, ensuring the strategy's robustness throughout the process.
#### Dependencies
1) pandas
2) numpy
3) yfinance
4) pandas-ta
5) statsmodels
6) PyPortfolioOpt
