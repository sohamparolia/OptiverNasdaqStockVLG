# Optiver-Nasdaq-Stock Exchange-VLG
open project created by Soham Parolia to predict closing price movements (target) for hundreds of Nasdaq listed stocks using data from the order book and the closing auction of the stock. 

## Table of Contents

- Introduction
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

## Features and Models Used

The main models used are:
1. LightGBM (default)
2. LSTM
3. Random Forest Regressor
The features used for prediction include essential information about each stock and its corresponding auction dynamics. These features encompass stock-specific identifiers (stock_id), date identifiers (date_id), auction characteristics such as imbalance size and imbalance buy/sell flag, reference price, matched size, far price, near price, bid/ask prices, bid/ask sizes, weighted average price (wap), and additional temporal information like seconds in the bucket. The target variable, representing the 60-second future move in the weighted average price of the stock minus the 60-second future move of the synthetic index, is available in the training set. The synthetic index is a custom-weighted index of Nasdaq-listed stocks specifically constructed for this competition by Optiver. This project aims to explore and compare the performance of different models in capturing the intricate dynamics of stock price movements during closing auctions.

## Installation

Provide instructions on how to install your project. Include any dependencies and specific steps needed to get the project up and running.

```bash
# Example installation commands
git clone https://github.com/yourusername/yourproject.git
cd yourproject
pip install -r requirements.txt
