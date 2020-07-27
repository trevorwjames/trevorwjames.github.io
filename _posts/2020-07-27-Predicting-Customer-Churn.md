---
layout: post
title: Predicting Customer Adherence
subtitle: Utilizing a Telecommunication Data set in order to predict Churn
cover-img: /assets/img/manhattanskyline.jpeg
tags: [marketing, sales, telco, machinelearning]
---

## What makes a "Sticky" Customer

The term sticky is just like it sounds. Someone that stays around and sticks to the subscription for a long time. In the battle of CLV (Client Lifetime Value) The goal is to earn customers that buy and keep on buying. This idea comes from the old addage "I would Rather make 10k/week for the rest of my life than 1 Million dollars once". For Businesses that sell a subscription based service LCV and ACV (Average Client Value) are the two biggest ways they evaluate how the business is running. For the purpose of this project we are going to stay focused on LCV. 

In order to understand LCV you need 2 numbers. 1. Monthy Revenue from that customer(Montly Charges), 2. Number of months (Tenure). That yeilds the total amount of money that customer brings in (Total Charges). We have two options in order to increase LCV, increase monthly charges or increase the number of months the customer pays. For the purpose of this project we will focus on an idea called "Churn"

## What is Churn?

Churn is also known as attrition, this is when a customer "falls off" Or cancels service. In the fight for High LCV attrition is the #1 Enemy. Here is where we find our useful target for prediction. Can we predict, based on a description of the customer, if they are going to "Churn". 

## Predictive Modeling or Machine Learning

Personally I like the sound of Predictive Modeling, over Machine Learning. The idea that I am creating a machine that learns based off of a set of characterstics in order to produce or predict an outcome is a little over my head. I guess I can connect with the "black box" idea a little better. 

So out goal is to use a set of features or "dependent variables" in order to predict a target or "independent variable". After getting the data all ready for processing running through multiple different models in order to find the one that gave us the "Best" result. Best in this case meaning the highest probability that the prediction that the model comes out with is the same as it would be in real life. Using a mertic call Reciever Operating Characteristic - Area Under the Curve will be the number that compares our models. 


### Link to Github repository & data set source 

[Github project repository](https://github.com/trevorwjames/Build-Week-1)

[AirBnb Data Set](http://insideairbnb.com/get-the-data.html)


