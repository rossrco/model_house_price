# Model House Price
In this project, we use a dataset collected by the *Curious Bot Homes* crawler and model the asking price of a real estate. The purpose of this exercise is to be able to estimate when a property is undervalued i.e. its predicted asking price is lower (by a certain margin) than the actual asking price.

## Problem Definition
A prudent purchase of real estate requires a good knowledge of the market. Subject matter experts (in this case real estate agents) usually develop an intuitive knowledge of the market. That is, they build up experience over several years in order to be able to evaluate a property.

Unfortunately, we cannot invest the same amount of time, but we need to achieve a comparable result in order to make a prudent purchase. Therefore, we have will attempt to model the market. Thus, our problem is:

> To develop a model that has less than 50 000 USD error on a 65 $m^2$ apartment.
