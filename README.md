# Optiver-Nasdaq-Stock Exchange-VLG
open project created by Soham Parolia to predict closing price movements (target) for hundreds of Nasdaq listed stocks using data from the order book and the closing auction of the stock. 

## Table of Contents

- Introduction
- Dataset
- Features and Models Used
- Installation
- Usage

## Introduction
![Alt text](https://github.com/sohamparolia/OptiverNasdaqStockVLG/blob/main/nasdaq.png)
The Nasdaq Stock Market (National Association of Securities Dealers Automated Quotations Stock Market) is an American stock exchange based in New York City. It is the most active stock trading venue in the US by volume, and ranked second on the list of stock exchanges by market capitalization of shares traded.
My project, a machine learning one, predicts the target variable, denoting the closing price movements of the stock. It is the 60 second future move in the wap of the stock, less the 60 second future move of the synthetic index. It is only provided for the train set.
The project comprises of mainly 3 steps:
1. Exploratory Data Analysis (including data processing, filling in missing values)
2. Model training and predictions
3. API Implementation

## Dataset
Dataset is available an can be downloaded from "https://www.kaggle.com/competitions/optiver-trading-at-the-close/data". The dataset comprises of below mentioned features and several files.
sample_submission: A valid sample submission, delivered by the API. See this notebook for a very simple example of how to use the sample submission.

revealed_targets: When the first time_id for each date (i.e. when seconds_in_bucket equals zero) the API will serve a dataframe providing the true target values for the entire previous date. All other rows contain null values for the columns of interest.

public_timeseries_testing_util.py: An optional file intended to make it easier to run custom offline API tests. See the script's docstring for details. You will need to edit this file before using it.

example_test_files/: Data intended to illustrate how the API functions. Includes the same files and columns delivered by the API. The first three date ids are repeats of the last three date ids in the train set, to enable an illustration of how the API functions.

optiver2023/: Files that enable the API. Expect the API to deliver all rows in under five minutes and to reserve less than 0.5 GB of memory. The first three date ids delivered by the API are repeats of the last three date ids in the train set, to better illustrate how the API functions. You must make predictions for those dates in order to advance the API but those predictions are not scored.

## Features and Models Used

The main models used are:
1. LightGBM (default)
2. LSTM
3. Random Forest Regressor
The features used for prediction include essential information about each stock and its corresponding auction dynamics. These features encompass stock-specific identifiers (stock_id), date identifiers (date_id), auction characteristics such as imbalance size and imbalance buy/sell flag, reference price, matched size, far price, near price, bid/ask prices, bid/ask sizes, weighted average price (wap), and additional temporal information like seconds in the bucket. The target variable, representing the 60-second future move in the weighted average price of the stock minus the 60-second future move of the synthetic index, is available in the training set. The synthetic index is a custom-weighted index of Nasdaq-listed stocks specifically constructed for this competition by Optiver. This project aims to explore and compare the performance of different models in capturing the intricate dynamics of stock price movements during closing auctions.

## Installation

Instructions on how to install this project.
```bash
git clone https://github.com/sohamparolia/OptiverNasdaqStockVLG.git
```

## Usage

Here are some potential uses of this project:

1. Algorithmic Trading Strategies: Implementing the predictive models developed in this project could enhance algorithmic trading strategies. Traders could use the predicted price movements to make more informed decisions on when to buy or sell stocks.
2. Risk Management: Predictive models for stock price movements can be invaluable for risk management purposes. By anticipating potential price changes, investors and financial institutions can adjust their portfolios and risk exposure accordingly.
3. Market Analysis: The insights gained from the project can contribute to a deeper understanding of market dynamics. Analyzing the predicted closing price movements may reveal patterns and trends in stock behavior during closing auctions, which can be valuable for market analysts.
4. Portfolio Optimization: Investors can use the predictions to optimize their portfolios by adjusting the allocation of different stocks based on anticipated price movements. This could lead to more efficient and profitable investment strategies.
5. Trading Automation: Integrating the predictive models into trading systems could enable automated trading strategies. This automation can help execute trades based on the predicted stock movements, reducing the need for manual intervention.

