<!-- markdownlint-disable first-line-h1 -->
<!-- markdownlint-disable html -->
<!-- markdownlint-disable no-duplicate-header -->

<a name="top"></a>
<div align="center">
  <img src="./figures/logo.png" style="height: 250px;"/>
</div>

---

<div align="center">
   <a href="mailto:erik.staszewski@gmail.com"><b>Email Me</b></a> | <a href="https://www.linkedin.com/in/estaszewski/"><b>My LinkedIn</b></a></b></a>
</div>

This project is still WIP. The algorithmic trading component is not yet posted, please be patient! Results will evolve as improvements are made. Feedback is welcome.

## Introduction

This project seeks to predict the exchange rate of the US dollar to Japanese yen. The model uses historical data from a 10-year period lasting from 2015 to 2024 combined with market regime detection and a deep learning LSTM model. The predicted values are used in an algorithmic trading simulation for a 5-year period from 2020 to 2024. 

## Background

### Market Context

The US dollar-Japanese yen pair today is among the most traded and liquid currency pairs in the global foreign exchange market. The United States and Japan rank among the world's top five economies by nominal GDP, with service sectors dominating their economic output. Top US companies by market cap include Walmart (retail), Apple (tech), and JPMorgan Chase (finance), while Japan hosts companies like Toyota (automotive), Sony (tech), and Nintendo (video gaming).

From after the conclusion of World War 2 until 1972, the Japanese yen was pegged to the US dollar at 360 JPY per USD, and later from 1972 to 1973 at 308 JPY per USD. Since 1973, the Japanese yen has been a floating currency, subject to market forces. In recent years, the rate has ranged from 130 JPY to 160 JPY per USD. The scope of this project is limited to the time period from 2015 to 2024, however it is important to have background context.

### Literature & Technical Review

**$k$-means clustering** is one of the most commonly used clustering methods. It seeks to partition all observations into $k$ distinct clusters based on feature similarity. In the process, each data point is clustered with the nearest mean, minimizing intra-cluster variance. This method is particularly useful for regime detection in financial time-series data, as it can help uncover distinct market states (bull, bear, sideways), based on volatility and return characteristics. These regimes reflect differing levels of investor sentiment and macroeconomic conditions, which influence currency movements.

**Long short-term memory (LSTM)** networks are a form of recurrent neural network designed to model sequential dependencies. LSTMs introduce memory cells and gating mechanisms that allow information to persist across long sequences. This architecture makes the method useful for time-series prediction, where past values significantly influence future outcomes. 

## Methodology

### Data Collection

Daily US dollar-Japanese yen exchange rate data was obtained using the Yahoo Finance yfinance Python package, from January 1, 2015 to December 31, 2024, a 10-year period. From the dataset, only the Date and Close price columns are used for analysis. The data was cleaned and sorted chronologically to ensure consistency.

Using the Yahoo Finance Python package, yfinance, the daily exchange rate between the US dollar and Japanese yen is obtained through January 1, 2015 to December 31, 2024, a 10-year period. Only the Date and Close values are extracted for this analysis.

### Regime Detection

To identify the underlying market conditions, $k$-means clustering is applied to two engineered features derived from the Close price, daily log returns, and 20-day rolling volatility, both normalized to zero mean and unit variance. The algorithm was configured to detect 3 distinct regimes: Sideways, Bull, and Bear, which correspond to periods of low volatility with negligible returns, high volatility with positive returns, and high volatility with negative returns respectively. These regime labels were then assigned to each trading day and used as an input feature in the predictive model.

### Modeling

The predictive model consists of an LSTM neural network, designed to forecast the next day's US dollar-Japanese yen exchange rate. The model is trained on a rolling window of the previous 60 trading days, incorporating both the Close price and its associated regime label as input features. The dataset was split into two equal five-year periods: with the training period lasting from January 1, 2015 to December 31, 2019, and testing period lasting from January 1, 2020 to December 31, 2024.

### Algorithmic Trading

WIP

## Results

### Exchange Rate Predictions

The model achieved the following results on the test set:

* **Mean Absolute Error (MAE)**: 3.20%
* **Accuracy**: 95.39%

These are excellent results!

### Algorithmic Trading Returns

WIP
