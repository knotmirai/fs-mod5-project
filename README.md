# Module 5 Final Project

# Bitcoin Price Forecasting

Bitcoin is the longest-running and most well-known cryptocurrency, first released as open-source in 2009 by the anonymous Satoshi Nakamoto. Bitcoin serves as a decentralized medium of digital exchange, with transactions verified and recorded in a public distributed ledger (the blockchain) without the need for a trusted record-keeping authority or central intermediary. Transaction blocks contain an SHA-256 cryptographic hash of previous transaction blocks and are thus "chained" together, serving as an immutable record of all transactions that have ever occurred. As with any currency/commodity on the market, bitcoin trading and financial instruments soon followed the public adoption of bitcoin and continue to grow. **Can we predict the price of bitcoin?**

This Kernel is divided into two parts:-

* Data Exploration
* Time Series Forecasting (Univariate/Multivariate)

**Univariate time series:** Only one variable is varying over time. For example, data collected from a sensor measuring the temperature of a room every second. Therefore, each second, you will only have a one-dimensional value, which is the temperature

**Multivariate time series:** Multiple variables are varying over time. For example, a tri-axial accelerometer. There are three accelerations, one for each axis (x,y,z) and they vary simultaneously over time.

And further for the **Time Series Forecasting:**-

1. Time Series Forecasting with **Prophet**
2. Time Series Forecasting with **LSTM**

## The Dataset

### 1. Historical Bitcoin Price

Bitcoin price history can be obtained from many sources such as Yahoo Finance, Coinbase, and so on.

This dataset contains:

* Start Time Period
* End Time Period
* Open Time
* Close Time
* Open Price
* Close Price
* High Price
* Low Price
* Trade Volume
* Trade Count
* Crypto Fear and Greed Index

### 2. Crypto Fear and Greed Index

Each day, the website https://alternative.me/crypto/fear-and-greed-index/ publishes this index based on analysis of emotions and sentiments from different sources crunched into one simple number: The Fear & Greed Index for Bitcoin and other large cryptocurrencies.

**Why Measure Fear and Greed?**

The crypto market behaviour is very emotional. People tend to get greedy when the market is rising which results in FOMO (Fear of missing out). Also, people often sell their coins in irrational reaction of seeing red numbers. With our Fear and Greed Index, we try to save you from your own emotional overreactions. There are two simple assumptions:

Extreme fear can be a sign that investors are too worried. That could be a buying opportunity.
When Investors are getting too greedy, that means the market is due for a correction.
Therefore, we analyze the current sentiment of the Bitcoin market and crunch the numbers into a simple meter from 0 to 100. Zero means "Extreme Fear", while 100 means "Extreme Greed". See below for further information on our data sources.

This dataset contains:

* Fear and Greed Value
* Fear and Greed Classification

## Data Exploration

![Historical-Price](https://knotmirai.com/wp-content/uploads/2022/01/Capture-1200x467.jpg)

![Trade-Count](https://knotmirai.com/wp-content/uploads/2022/01/Capture-3-1200x491.jpg)

![Trade-Volume](https://knotmirai.com/wp-content/uploads/2022/01/Capture-2-1200x498.jpg)

![Fear&Greed Value](https://knotmirai.com/wp-content/uploads/2022/01/Capture-1-1200x497.jpg)

![Correlation](https://knotmirai.com/wp-content/uploads/2022/01/download-1.png)

![Decomposition](https://knotmirai.com/wp-content/uploads/2022/01/download.png)

## Time Series Forecasting

Time Series data is an experimental data which has been observed at different points in time (usually evenly spaced, like once a day or once an hour or once a minute). For example, the data of airline ticket sales per day is a time series. However, just because a series of events has a time element does not automatically make it a time series, such as the dates of major airline disasters, which are randomly spaced and are not time series. These types of random processes are known as point process.

Time Series have several key features such as trend, seasonality, and noise. Forecasting is the process of making predictions of the future, based on past and present data. 

Here in this kernel, we attempt to perform Time Series Analysis on the Historic Bitcoin Price data. We can easily see from the **Data Exploration** section, that the Bitcoin prices were quite volatile and inconsistent over the years.  Its very hard to perform Time series analysis on such volatile data. But here we try to explore the different Time series forecasting models. All the models used in this Kernel are models that can probably handle the non-stationarity data like bitcoin price.

### 1. Time Series Forecasting with Prophet

Prophet is a procedure for forecasting time series data based on an additive model where non-linear trends are fit with yearly, weekly, and daily seasonality, plus holiday effects. It works best with time series that have strong seasonal effects and several seasons of historical data. Prophet is robust to missing data and shifts in the trend, and typically handles outliers well.

#### Prophet Univariate Result

![Prophet-Univariate](https://knotmirai.com/wp-content/uploads/2022/01/download-2.png)

#### Prophet Multivariate Result

![Prophet-Multivariate](https://knotmirai.com/wp-content/uploads/2022/01/download-3.png)

### 2. Time Series Forecasting with  LSTM

LSTM units are units of a recurrent neural network (RNN). An RNN composed of LSTM units is often called an LSTM network (or just LSTM). A common LSTM unit is composed of a cell, an input gate, an output gate and a forget gate. The cell remembers values over arbitrary time intervals and the three gates regulate the flow of information into and out of the cell.

#### LSTM Univariate Result

![LSTM-Univariate](https://knotmirai.com/wp-content/uploads/2022/01/Capture-4-1200x541.jpg)

#### LSTM Multivariate Result

![LSTM-Multivariate](https://knotmirai.com/wp-content/uploads/2022/01/Capture-5-1200x505.jpg)

## Summary

* LSTM model can handle the data like bitcoin price better than Prophet model and give the better result.
* RSME of LSME model is ~1900.
* The more factor we included; the better prediction result we will obtain.

## Future Plan

* Try another type of model for better results.
* Parameters tuning or optimization.
* Add another factor such as Twitter posts from influencers.
* Create our own fear and greed index.
