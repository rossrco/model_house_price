# Model House Price
In this project, we use a dataset collected by the *Curious Bot Homes* crawler and model the asking price of a real estate. The purpose of this exercise is to be able to estimate when a property is undervalued i.e. its predicted asking price is lower (by a certain margin) than the actual asking price.

## Problem Definition
A prudent purchase of real estate requires a good knowledge of the market. Subject matter experts (in this case real estate agents) usually develop an intuitive knowledge of the market. That is, they build up experience over several years in order to be able to evaluate a property.

Unfortunately, we cannot invest the same amount of time, but we need to achieve a comparable result in order to make a prudent purchase. Therefore, we have will attempt to model the market. Thus, our problem is:

> To develop a model that has less than 50 000 USD error on a 65 $m^2$ apartment.

## Exploratory Visualization And Analysis
### Dashboard
We set up a dashboard in Google Data Studio with some of the data we collect in *Curious Bot Homes*. This allows us to:

* Develop an intuition about the problem. This answers questions such as:
    * What is the ratio of the various property types in general?
    * How big is a median property in the area of interest?
    * What kind of properties get promoted?
* Develop an understanding about the real estate market. This answers questions such as:
    * How does the price trend develop over time?
    * How many ads per day / week / month appear in the target area?

![Real Estate Dashboard](https://github.com/rossrco/model_house_price/img/dashboard.png)

### Geographical Visualization
Understanding the property market also includes developing an intuition about the price in various parts of the target area. In the long run, this also allows us to understand our model's predictions and to be discerning about the validity of said predictions.

To achieve that, we set up a Kepler GL visualization with the following layers:

* The median price per hexagon
* The mode of the real estate type per hexagon
* The median real estate area per hexagon

![Real Estate Geographical Visualization](https://github.com/rossrco/model_house_price/img/geo_visualization.png)

### Exploratory Data Analysis
To gain insights into the raw data and develop robust statistical models, we performed a quick [exploratory data analysis](https://github.com/rossrco/model_house_price/eda.ipynb). In it, we explore mainly the area and price distributions for normal values as well as outliers (i.e. price having `z-score >= 3`).

![Price Per Property Type](https://github.com/rossrco/model_house_price/img/price_per_property_type.png)

## Benchmark
Our selected benchmarks are:
* The median price of all properties in the train dataset
* The median price per post code for all post codes in the train dataset

| Model Name                             | explained_variance | mean abs error | mean percentage error | r2 score |
|----------------------------------------|--------------------|----------------|-----------------------|----------|
| [Benchmark] Median Price               | 0%                 | 16586          | 27%                   | -0%      |
| [Benchmark] Median Price Per Post Code | 27%                | 13584          | 22%                   | 26%      |

## Algorithms And Techniques
We will experiment with the following algorithms:
* Linear Models:
    * Linear Regression
    * Gradient Boosting Regressor
* Deep Learning:
    * 3 Hidden Layer Neural Network
    * Wide And Deep Regressor

