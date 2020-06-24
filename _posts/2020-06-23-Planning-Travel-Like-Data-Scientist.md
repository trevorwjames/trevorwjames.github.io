---
layout: post
title: Traveling Like a Data Scientist
subtitle: Using AirBnB Data to make decisions on where to stay in the Big Apple
cover-img: /assets/img/manhattanskyline.jpeg
tags: [travel, airbnb, NYC]
---

## Finding a place to stay in New York City can be stressful...

Rather than relying on the pictures, the wordy descriptions, and the "fluffy" stuff. Let's let the data decide what AirBnB we should select for our journey to the big apple. 

When you have the job of reserving a room for your trip, there are so many different options to take into consideration. Price, location, reviews, looks, host, etc. what we have done here is take a small portion of the objectivity out of it and look to understand our options based upon the **Data!**
Despite Manhattan being just under 23 square miles, there are 33 different unique "neighborhoods" that AirBnB uses to identify the area in which the reservation is located in. In order to make it a little easier to search for prices I would look at the average price per neighborhood. This would make it a little easier to search if I could filter down to the neighborhoods that had a reasonable price range.

<iframe style="border-width:0" src="https://charts.sharpdesigndigital.com/trevor-manhattanavg.html" width="700" height="775"> </iframe>

We can clearly see some things from the average price per neighborhood, it may take a little reaserch outside just our data, because just going for the cheapest neighborhood in manhattan could put as a ways away from what we want to see and do! Despite thinking that oh "Inwood, or Marble Hill is the way to go.", that would put us a ways away from the action.

Just for fun, let's take a look at the most expensive area, say we won the lottery and we want to have some fun! Tribeca, the red highlighted bar on the figure above, is clear and away the most expensive place to stay averaging just about 490$/night.

In my experience when you charge top dollar for a place to stay you should have nothing but raving reviews right? We don't have access to the quality of reviews, but we do have access to the number of reviews. Does the price of where you stay have any connection with the number of reviews?

<iframe style="border-width:0" src="https://charts.sharpdesigndigital.com/trevor-tribecreviewsprice.html" width="725" height="375"> </iframe>

Say we haven't won the lottery, yet. Lets select abother neightborhood that is more in our price range. Contrary to popular belief, Harlem is a very up and coming area that is a short train ride away from some awesome attractions downtown. If you use the same guildines as above. We can pick out a place to stay that is in our price range, as well as if that one in our range has some reviews.

<iframe style="border-width:0" src="https://charts.sharpdesigndigital.com/trevor-harlemreviews.html" width="725" height="375"> </iframe>

There _are_ some variables we have left out when it comes to selecting a place to stay. Being able to see a few photos, actually read the reviews to see how positive they are, and maybe even looking into the host a touch, can have a big impact on where to stay. What we did do though is take out the bias of either paid advertisements popping up first, or letting the search engine show us what it thinks we are looking for. 

Think twice next time before you just select the AirBnB that pops up first on your serach, there are thousands of options. Explore wisely. 

