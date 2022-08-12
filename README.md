# Dogecoin Price Prediction

****

## 🔍 About this project 

The aim of this project is to predict the dogecoin's close price in the future in order to make good decisions at the stock market.

You can download the dataset at Finance Yahoo's page, searching for "Dogecoin", clicking at "Historical Data" and then download. Or just <a href="https://finance.yahoo.com/quote/DOGE-USD/history?p=DOGE-USD">click here</a>

## 🗃️ Project topics

This project is divided in the following topics:
<ol>
  <li> Imports
  <li> Data Description
  <li> Extracting Features
  <li> Descriptive Analysis
  <li> The Prediction
</ol>

## 📍 Dataset Description

First of all, let's see the first 5 rows of our dataset

<img src="https://i.ibb.co/kx24MsK/Top-5-rows.png">

The dimension of this dataset is 1736 x 7, with daily close prices since 11/09/2017. 

About the missing values, we don't have any. And all the features are float64 type, except "Date", which is datetime.

Below you can see the global statistical analysis:

<img src="https://i.ibb.co/MkmZWGq/Screenshot-8.png">

We can see that Adj Close column is equal to Close column, so we can exclude it to make the dataset more clean.

## 🗺️ Descriptive Analysis

Let's start visualizing the graph that shows the close price variation during the period

<img src="https://i.ibb.co/YpN2bRp/Screenshot-1.png">

We can clearly see that the most important part of this analysis is between 2021 and 2022, so let's take a look more closer. Starting with 2021:

<img src="https://i.ibb.co/bNHf68T/Screenshot-2.png">

In this period, we reach the maximum close price of dogecoin at 05/07/2021. 

Now, 2022:

<img src="https://i.ibb.co/852fmCZ/Screenshot-3.png">

We can see that the price started falling down again.

I know that when we talk about stock market we try to profit with it. So, nothing is better than looking at moments that gave to the investitors the biggest profits. I'm gonna look just at 2021, which was the year of price boom. And to start this analysis, let's take a look at the daily and monthly close price variation:

<img src="https://i.ibb.co/wBGfb4Q/Screenshot-4.png">

In 2021, we had 884 days with positive close price variation; 844 days with negative close price variation; and 8 days with no close price variation. In addition, the maximum postive price variation was 0.1433. And the minimum negative price variation was -0.1843 in a day.

Now, let's see the montly close price variation

<img src="https://i.ibb.co/fkFBKbX/Screenshot-5.png">

We had 6 months with positive price variation and 6 months with negative price variation.

Ok, we saw the variations between dates in the same year, but we know that some people invest their money and keep it there for years to get a great profit. So we need to look at the whole dataset, and this is what I did. 

I created a loop to tell me all the profits greater than 100% between all the dates since 2017. Take a look:

<img src="https://i.ibb.co/zs316cW/Screenshot-9.png">

Analysing this dataframe, we can extract the following insights of 2021:

<ul>
  <li> The average number of days to have a profit between 100% and 200% was 172 
  <li> The average profit was 12.22x
  <li> The max profit was 157.57x, and it happened buying at 2021/01/01 and selling at 2021/05/08, i.e. 127.0 days between the buy and sell
</ul>

## 📈 The Prediction

To predict the dogecoin's close price, I used autots package. According to it's official documentation, AutoTS is a time series package for Python designed for rapidly deploying high-accuracy forecasts at scale. 

There are dozens of forecasting models usable in the sklearn. These includes naive, statistical, machine learning, and deep learning models.

After predicting, these are the values that the algorithm returned:

<img src="https://i.ibb.co/GQVBCwt/Screenshot-6.png">

Plotting in a graphic:

<img src="https://i.ibb.co/cJCGzWZ/Screenshot-7.png">
