<!-- markdownlint-disable first-line-h1 -->
<!-- markdownlint-disable html -->
<!-- markdownlint-disable no-duplicate-header -->

<a name="top"></a>
<div align="center">
  <img src="./figures/USDJPY.png" style="width: 300px;"/>
</div>

<div style="display: flex; justify-content: center;">
  <h1 style="max-width: 900px; text-align: center;">
    USD/JPY Rate Prediction Model
  </h1>
</div>

---

<div align="center">
   <a href="mailto:erik.staszewski@gmail.com"><b>Email Me</b></a> | <a href="https://www.linkedin.com/in/estaszewski/"><b>My LinkedIn</b></a></b></a>
</div>

This project is still WIP. Results will evolve as improvements are made. Feedback is welcome.

## Introduction

This project seeks to predict the exchange rate of the US dollar to Japanese yen. The model uses historical data combined with market regime detection and a deep learning LSTM model.

In later stages, the predicted values will be used in an an algorithmic trading simulation.

## Background

### Market Context

The US dollar to Japanese yen pair today is one of the most traded and liquid currency pairs in the global foreign exchange market.

From after the conclusion of World War 2 until 1972, the Japanese yen was pegged to the US dollar at 360 JPY per USD, and later from 1972 to 1973 at 308 JPY per USD. Since 1973, the Japanese yen has been a floating currency, subject to market forces. In recent years, the rate has ranged from 130 JPY to 160 JPY per USD.

### Literature & Technical Review

**$k$-means clustering** is one of the most commonly used clustering methods. It seeks to partition all observations into $k$ clusters, helping identify distinct regimes.

**Long short-term memory (LSTM)** is a type of recurrent neural network. The memory structure of LSTMs allow it to capture long-term dependencies and lag relationships, making it ideal for time-series datasets.

## Methodology

### Data Collection

Using the Yahoo Finance Python package, yfinance, the daily exchange rate between the US dollar and Japanese yen is obtained through January 1, 2015 to December 31, 2024, a 10-year period. Only the Date and Close values are extracted for this analysis.

### Regime Detection

$k$-means clustering is used to detect the regimes, using data from normalized daily returns and 20-day rolling volatility. Three distinct regimes are classified: Sideways, Bull, Bear. The regimes are used as input features in the predictive model.

### Modeling

An LSTM neural network is used to forecast the exchange rate for the following day, trained on a 60-day rolling window of past Close values and the corresponding regime labels.

The training and testing periods are equal, with the training period lasting from January 1, 2015 to December 31, 2019, and testing period lasting from January 1, 2020 to December 31, 2024.

## Results

### Exchange Rate Predictions

The model achieved the following results on the test set:

* **Mean Absolute Error (MAE)**: 3.20%
* **Accuracy**: 95.39%

These are excellent results!
