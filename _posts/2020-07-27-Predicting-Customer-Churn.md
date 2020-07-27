---
layout: post
title: Predicting Customer Adherence
subtitle: Utilizing a Telecommunication Data set in order to predict Churn
cover-img: /assets/img/manhattanskyline.jpeg
tags: [marketing, sales, telco, machinelearning]
---

## Finding a place to stay in New York City can be stressful...

Rather than relying on the pictures, the wordy descriptions, and the "fluffy" stuff. Let's let the data decide what AirBnB we should select for our journey to the big apple. 

When you have the job of reserving a room for your trip, there are so many different options to take into consideration. Price, location, reviews, looks, host, etc. What we have done here is take a small portion of the objectivity out of it and look to understand our options based upon the **Data!**
Despite Manhattan being just under 23 square miles, there are 33 different unique "neighborhoods" that AirBnB uses to identify the area in which the reservation is located in. In order to make it a little easier to search for prices I took a look at the average price per neighborhood. This would make it a little easier to search if I could filter down to the neighborhoods that had a reasonable price range.

### What Price looks Right??

<iframe style="border-width:0" src="https://charts.sharpdesigndigital.com/trevor-manhattanavgsbig.html" width="900" height="750"> </iframe>

We can clearly see some things from the average price per neighborhood, it may take a little reaserch outside just our data, because just going for the cheapest neighborhood in manhattan could put as a ways away from what we want to see and do! Despite thinking that oh "Inwood, or Marble Hill is the way to go.", that would put us a ways away from the action. Before we choose our realistic option for where we would want to stay, lets have a little fun first. 

### If Money grew on trees...

Let's take a look at the most expensive area, say we won the lottery and we want to have a 5 star experience via AirBnB! Tribeca, the red highlighted bar on the figure above, is clear and away the most expensive place to stay averaging just about 490$/night.

In my experience when you charge top dollar for a place to stay you should have nothing but raving reviews right? We don't have access to the quality of reviews, but we do have access to the number of reviews. Does the price of where you stay have any connection with the number of reviews? (_Zoom in on the chart and hover over the points to see more info about each location_)

<iframe style="border-width:0" src="https://charts.sharpdesigndigital.com/trevor-tribecreviewspricebig.html" width="865" height="450"> </iframe>

Huh, so it looks like if youre planning on spending over 800$/night on a place to stay, there wont be as many people reviewing it. That makes sense to a degree, how many people are actually spending that much on a night in an AirBnB. A loft in Tribeca with a private elevator does sound pretty delightful though. 

### Back to Reality

Say we haven't won the lottery, yet. Lets select abother neightborhood that is more in our price range. Contrary to popular belief, Harlem is a very up and coming area that is a short train ride away from some fantastic attractions downtown. Also, in order to view the options we have im going to limit the options on the chart below to $500/night or less. If you use the same guidelines as above. We can pick out a place to stay that is in our price range. Also we can compare how reviewed each place is as well. 

<iframe style="border-width:0" src="https://charts.sharpdesigndigital.com/trevor-harlemreviewsbig.html" width="865" height="450"> </iframe>

Now that we have a better idea of where we want to look, eliminated some of the "fluff" that comes with inadequte searches and paid advertising through the app. We can make **much** better decisions based on the visual prarmeters provided. The "Spacious Harlem Garde Apartment" with hosts Alex and Maya, for 155$/night and just under 140 reviews sounds like a winner! 


## Final Thoughts

There are _some_ variables we have left out when it comes to selecting a place to stay. Being able to see a few photos, actually read the reviews to see how positive they are, and maybe even looking into the host. All good things that you could do now that you have a more clear picture of what the landscape of renting an AirBnB in New York City looks like! 

Think twice next time before you just select the AirBnB that pops up first on your search, there are thousands of options. Explore accordignly. 


### Link to Github repository & data set source 

[Github project repository](https://github.com/trevorwjames/Build-Week-1)

[AirBnb Data Set](http://insideairbnb.com/get-the-data.html)


