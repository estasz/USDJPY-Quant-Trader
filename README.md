<!-- markdownlint-disable first-line-h1 -->
<!-- markdownlint-disable html -->
<!-- markdownlint-disable no-duplicate-header -->

<a name="top"></a>
<div align="center">
  <img src="./figures/USDJPY.png" style="width: 300px;"/>
</div>

---

<div align="center">
   <a href="mailto:erik.staszewski@gmail.com"><b>Email Me</b></a> | <a href="https://www.linkedin.com/in/estaszewski/"><b>My LinkedIn</b></a></b></a>
</div>

This project is still WIP. Results will evolve as improvements are made. Feedback is welcome.

## Introduction

This project seeks to predict the exchange rate of the US dollar to Japanese Yen.

Later on, the obtained predicted values will be utilized in an algorithmic trading simulation.

## Background

### Market Context

The US dollar to Japanese yen pair today is one of the most traded currency pairs globally.

From after the conclusion of World War 2 until 1972, the Japanese yen was pegged to the US dollar at a rate of 1 USD to 360 JPY, and later from 1972 to 1973 at 1 USD to 308 JPY. Since 1973, the Japanese yen has been a floating currency.

### Literature & Technical Review

**$k$-means clustering** is one of the many clustering methods used in data mining. It seeks to partition all the $n$ observations into $k$ clusters. 

A **Long short-term memory (LSTM)** is a type of Recurrent Neural Network.

## Methodology

### Data Collection

Using the Yahoo Finance Python function, yfinance, the exchange rate between the US dollar and Japanese yen is obtained through January 1, 2015 to December 31, 2024, a 10-year period. Only the Date and Close values are extracted for this analysis.

### Regime Detection

$k$-means clustering is used to detect the regimes.

### Modeling

LSTM (Long-Short Term Memory)

### Algorithmic Trading

To Be Determined!

## Results

### Exchange Rate Predictions

Mean Absolute Error (MAE): 3.20%

Accuracy: 95.39%

### Algorithmic Trading Profit & Loss

To Be Determined!

## Model Robustness Testing

To Be Determined!

### Sensitivity Analysis

To Be Determined!

### Statistical Testing

To Be Determined!

### Stress Testing

To Be Determined!

## Conclusion
