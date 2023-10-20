# Stock Price Prediction with NLP and Deep Learning

## Abstract

This research project explores the application of natural language processing in tandem with a deep neural network to forecast daily changes in the Dow Jones Industrial Average (DJIA). The model demonstrated a slight improvement over random guessing in predicting market movements.

## Introduction

This project delves into predicting stock price movements, a crucial aspect of the trillion-dollar financial industry. Traditionally, this domain was accessible only to large financial institutions and expert analysts. However, with the advent of publicly available market data, independent investors have gained access to valuable information for making informed investment decisions.

While the stock market exhibits an overall trend, attempts to consistently outperform it have yielded mixed results. This is due to the complexity of factors influencing stock prices, including microeconomic trends and consumer preferences, which can be challenging to forecast even for experts.

The focus here is on predicting the DJIA, a key indicator of the American economy. Past studies have shown that macroeconomic trends can be forecasted based on daily news, and even news headlines alone can yield similar results.

## Dataset and Features

The dataset comprises DJIA prices and daily news articles, publicly available from Kaggle. It spans from August 8, 2008, to July 1, 2016. DJIA data includes opening and closing prices, daily trading volume, high, and low for each market day. News data consists of the 25 most popular headlines sourced from Reddit News for each day.

Additional features include the previous 5 days’ stock price changes, acknowledging the influence of recent market trends. These features are structured into a two-dimensional array, resulting in a (1988,5) NumPy array.

## Methods

The neural network architecture takes into account the sequential nature of the data. Each day has 25 news headlines, along with the difference in DJIA stock price between time `t` and `t-1`. The model predicts the amount the stock price will rise or fall, rather than the actual price. The data is normalized for training by subtracting the mean and dividing by the standard deviation of the stock price changes.

The baseline model employs a sentiment analysis approach using a CNN and RNN on sentence embeddings. An LSTM is incorporated to capture long-term dependencies. Additionally, the change in stock market price for the previous twenty days is fed into an LSTM, which serves as an additional input.

## Experiments

The baseline model, relying solely on news data, achieved a 54% accuracy in predicting stock market movements. Hyperparameter tuning involved variations in learning rates, dropout rate, number of layers, elements in the LSTM, and convolution layers. Grid and random search were utilized to identify optimal values.

A logistic regression model using NYC weather data achieved 52% accuracy in predicting DJIA price movements, indicating a marginally better performance than chance.

## Results

The final model, incorporating previous stock price changes and global news headlines, achieved an accuracy of 61.31% with a mean absolute error of 71.40. While the model excelled at binary classification, it faced challenges in accurately determining the magnitude of stock price changes.

## Conclusion

This project demonstrated an improvement over a baseline model in predicting daily DJIA movements. While the model's performance is marginally better than chance, it surpasses the capabilities of many human analysts. The incorporation of historical market data proved beneficial, suggesting potential avenues for further enhancement, such as incorporating alternate data sources or focusing on company-specific news.

