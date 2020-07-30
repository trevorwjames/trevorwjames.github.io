---
layout: post
title: Predicting Customer Adherence
subtitle: Utilizing a Telecommunication Data set in order to predict Churn
cover-img: assets/img/shutterstock_377215789_0.jpg
tags: [marketing, sales, telco, machinelearning]
---

## What makes a "Sticky" Customer

The term sticky is just like it sounds. Someone that stays around and sticks to the subscription for a long time. In the battle of LCV (Lifetime Client Value) The goal is to earn customers that buy and keep on buying. This idea comes from the old addage "I would Rather make 10k/week for the rest of my life than a Million dollars once". For Businesses that sell a subscription based service LCV and ACV (Average Client Value) are the two biggest ways they evaluate how the business is running. For the purpose of this project we are going to stay focused on LCV. 

In order to understand LCV you need two numbers. 1. Monthy Revenue from that customer(Montly Charges), 2. Number of months (Tenure). That yeilds the total amount of money that customer brings in (Total Charges). We have two options in order to increase LCV, increase monthly charges or increase the number of months the customer pays. For the purpose of this project we will focus on an idea called "Churn"

## What is Churn?

Churn is also known as attrition, this is when a customer "falls off" or cancels service. In the fight for High LCV, attrition is the #1 Enemy. Here is where we find our useful target for prediction. Can we predict, based on a description of the customer, if they are going to "Churn". In order to have a starting point that will allow us to prove our model is better than just guessing the average, We use a baseline. First and formost our goal is predicting one of two outcomes - if the customer will discontinue service or remain with the service. This means that if churn is "True" the customer will terminate or cancel service. If "False" the customer will remain with the service. A little confusing at first. Although we can break it down to saying True is bad and False is good!. 

<img src="/assets/img/carbon (1).png">

## Data Preperation

Our goal is to use a set of features or "independent variables" in order to predict a target or "dependent variable". After cleaning up a few columns in our dataset, the first task was to break apart the features from the target. In order to have an honest model that can truly predict, rather than just read btw the lines, we perform a train, validation, test split of the data. Meaning we have a large set in which the model will use to learn the in's and out's of how to predict churn. A set to make sure that it can be geenralized and compared. Then a set that we do not touch until we are ready to run our model one last time.

## Metrics

We will try a few different model types in order to find the one that gave us the "Best" result. Best in this case meaning the highest probability that the prediction that the model comes out with is the same as it would be in real life. We will use 2 metrics primarliy in order to understand our model. First is ROC-AUC, Second is Recall.

## And The Winner is...

We like to be as "Scientific" as posible when looking at a problem. This is always the best way to go about findig the simplest solution for a complex problem. The problem at hand is one that we can categorise as a supervised classfication problem. This means we are able to identify our target variable, and that taget variable that we are attempting to predict is binary. We start with the simplest form of predictive modeling for classification. Logistical Regression, this modeling style using a regression equation to create a line that "Fits" the probability of the features resulting in a certain outcome. Although in normal regression that line would be relatively straight. In our case because we have only two options, our line looks more like an "S". After being as scientific as possible and running through a multitude of options, the best model is actuall where we started. A Logistic Regression model. Based on an ROC-AUC score of 84.3%, and a recall score of 90%, we have come across a model that we can use to predict to a high probability that a customer will Churn.

<img src="/assets/img/lin model.png"> 

ROC-AUC is the Reciever Operating Charateristic and Area under the Curve. This is a measure of how our predicitions will compare to the actual results. Resulting in True and False Positives, as well as True and False Negatives. This can be extremely import factors when it comes to life or death scenarios. Because maintaining your service with a certain provider is not life or death. We are merely going to use this number in order to show what model performs best. 

<img src="/assets/img/ROC-AUC-curve.png">

- Below are the scores of our **Logisitic Regresssion** model and **XGBoost** Model, its closest competitor

<img src="/assets/img/ROC-AUC-carbon.png">

Recall is the number of True Positive predicted outcomes, out of the total number of precited outcomes. This is the score we are looking for when it comes to something in the marketing realm. We want to keep from losing as many people as possible, if we happen to target a group in which may not be at risk for churn, that is ok. The main goal is to include all that could possibily cancel service.  

<img src="/assets/img/carbon (2).png">

## Now What? 

Now that we have officially become fortune tellers, how do we use that power for the greater good? How can we use the mechanisms of our model to help shape the way our business handles our customer? Lets look at a few post modeling metrics that will give us insight on what features of our data have the largest impact on the outcome. First is the "Permutation Importance" This is a process of jumbling up each feature and re-inputting that feature into the model to see how much of an impact it will have on the outcome. This process gives us insight on which customer characteritic would be the most important, or the ideal place to focus our energy on in order to reduce attrition.

<img src="/assets/img/newplot.png">

From what we can see above the far and away number most important characteristic is "Tenure". The number of months a customer has been with the service. Well obviously this is important, because if they are still with the company they havent left yet... Lets look at it from a different lens. The longer a customer stays with a company, the more likely they are to continue service. That means if we are looking to increase the LCV of a customer, placing the focus on having them for a longer time, rather than a quick sell will make an exponential outcome down the road. This could help gear the sales team, or marketing team away from quick deals or fixes and more toward long term committments. 

The second most important characteristic that is involved in predicting Churn is "Total Charges". This is a function of the number of months they have been with the service and the "Monthly Charges" feature. The Total charges features is an extrapolation on the idea of Tenure. Although we are not exactly sure of the correlation... Is is those who spent more money, or less money? All we know right now is that the feature is important, we are not exactly sure what parts of the feature are important. For that lets look how how Tenure and Montlhy charges interact - after all, thats how we arrive at Total Charges. 

<img src="/assets/img/pdpinteract.png">

From this chart we can see those squares in yellow have a higher probability of Churn, that being the customers with a very _short_ tenure, and _high_ Monthly charges. Then as you move to a _long_ tenure and _low_ monthly charges we see the probabilty decrease. What can we do with this information to better run our business, or gear or goals as a sales team?

## Conclusions

There is still much to take into account when working on a predictive model like this, because I do not have as much background on the time frame of the dataset, the goals of the company, more in depth product knowledge, etc. I cant make hard suggestions. Although from our findings we can see that a lower customer monthly payment, combined with a decent tenure tends to mean they will stay with the company for longer. Directing the stragtegy of all parties involved to incentivize moderate priced monthly options with longer term commitments may be the way to create the growth the company is looking for. 

### Link to Github repository & data set source 

[Github project repository](https://github.com/trevorwjames/Build_week2)

[Telco Customer Churn Dataset](https://www.kaggle.com/palashfendarkar/wa-fnusec-telcocustomerchurn)


