---
layout: post
title: Traveling Like a Data Scientist
subtitle: Using AirBnB Data to make decisions on where to stay
cover-img: /assets/img/manhattanskyline.jpeg
tags: [travel, airbnb, NYC]
---

Research question - Rather than relying on the pictures, the wordy descriptions, and the fluffy stuff. Let's let the data decide what AirBnB we should select for our journey to the big apple. 

When you have the job of reserving a room for your trip, there are so many different options to take into consideration. Price, location, reviews, looks, host, etc. what we have done here is take a small portion of the objectivity out of it and look to understand our options base upon the Data!
Despite Manhattan being just under 23 square miles, there are 33 different unique "neighborhoods" that AirBnB uses to identify the area in which the reservation is located in. I thought in order to make it a little easier to search for prices I would look at the average price per neighborhood. This would make it a little easier to search if I could filter down to the neighborhoods that had a reasonable price range. (see chart of average per neighborhood)

{
  "$schema": "https://vega.github.io/schema/vega/v5.json",
  "background": "white",
  "padding": 5,
  "width": 400,
  "title": {
    "text": "Average AirBnB Price per night for different Neighborhoods in Manhattan",
    "frame": "group"
  },
  "style": "cell",
  "data": [
    {
      "name": "data-ff08b1bfe8d2846933cf4fe11db1a68e",
      "values": [
        {"neighborhood": "Midtown", "avg_price": 282.7},
        {"neighborhood": "Harlem", "avg_price": 119},
        {"neighborhood": "East Harlem", "avg_price": 133.2},
        {"neighborhood": "Murray Hill", "avg_price": 221},
        {"neighborhood": "Hell's Kitchen", "avg_price": 204.8},
        {"neighborhood": "Upper West Side", "avg_price": 210.9},
        {"neighborhood": "Chinatown", "avg_price": 161.5},
        {"neighborhood": "West Village", "avg_price": 267.7},
        {"neighborhood": "Chelsea", "avg_price": 249.7},
        {"neighborhood": "Inwood", "avg_price": 88.9},
        {"neighborhood": "East Village", "avg_price": 186.1},
        {"neighborhood": "Lower East Side", "avg_price": 186.3},
        {"neighborhood": "Kips Bay", "avg_price": 202.4},
        {"neighborhood": "SoHo", "avg_price": 287.1},
        {"neighborhood": "Upper East Side", "avg_price": 188.9},
        {"neighborhood": "Washington Heights", "avg_price": 89.6},
        {"neighborhood": "Financial District", "avg_price": 225.5},
        {"neighborhood": "Morningside Heights", "avg_price": 114.8},
        {"neighborhood": "NoHo", "avg_price": 295.7},
        {"neighborhood": "Flatiron District", "avg_price": 341.9},
        {"neighborhood": "Roosevelt Island", "avg_price": 113.3},
        {"neighborhood": "Greenwich Village", "avg_price": 263.4},
        {"neighborhood": "Little Italy", "avg_price": 222.1},
        {"neighborhood": "Two Bridges", "avg_price": 127.1},
        {"neighborhood": "Nolita", "avg_price": 230.1},
        {"neighborhood": "Gramercy", "avg_price": 222.8},
        {"neighborhood": "Theater District", "avg_price": 248},
        {"neighborhood": "Tribeca", "avg_price": 490.6},
        {"neighborhood": "Battery Park City", "avg_price": 367.6},
        {"neighborhood": "Civic Center", "avg_price": 191.9},
        {"neighborhood": "Stuyvesant Town", "avg_price": 169.1},
        {"neighborhood": "Marble Hill", "avg_price": 89.2}
      ]
    },
    {
      "name": "data_0",
      "source": "data-ff08b1bfe8d2846933cf4fe11db1a68e",
      "transform": [
        {
          "type": "filter",
          "expr": "isValid(datum[\"avg_price\"]) && isFinite(+datum[\"avg_price\"])"
        }
      ]
    }
  ],
  "signals": [
    {"name": "y_step", "value": 20},
    {
      "name": "height",
      "update": "bandspace(domain('y').length, 0.1, 0.05) * y_step"
    }
  ],
  "marks": [
    {
      "name": "layer_0_marks",
      "type": "rect",
      "style": ["bar"],
      "from": {"data": "data_0"},
      "encode": {
        "update": {
          "fill": [
            {"test": "(datum.neighborhood === 'Tribeca')", "value": "red"},
            {"value": "blue"}
          ],
          "x": {"scale": "x", "field": "avg_price"},
          "x2": {"scale": "x", "value": 0},
          "y": {"scale": "y", "field": "neighborhood"},
          "height": {"scale": "y", "band": true}
        }
      }
    },
    {
      "name": "layer_1_marks",
      "type": "text",
      "style": ["text"],
      "from": {"data": "data_0"},
      "encode": {
        "update": {
          "align": {"value": "left"},
          "baseline": {"value": "middle"},
          "dx": {"value": 3},
          "fill": [
            {"test": "(datum.neighborhood === 'Tribeca')", "value": "red"},
            {"value": "blue"}
          ],
          "x": {"scale": "x", "field": "avg_price"},
          "y": {"scale": "y", "field": "neighborhood", "band": 0.5},
          "text": {"signal": "format(datum[\"avg_price\"], \"\")"}
        }
      }
    }
  ],
  "scales": [
    {
      "name": "x",
      "type": "linear",
      "domain": {"data": "data_0", "field": "avg_price"},
      "range": [0, {"signal": "width"}],
      "nice": true,
      "zero": true
    },
    {
      "name": "y",
      "type": "band",
      "domain": {"data": "data_0", "field": "neighborhood", "sort": true},
      "range": {"step": {"signal": "y_step"}},
      "paddingInner": 0.1,
      "paddingOuter": 0.05
    }
  ],
  "axes": [
    {
      "scale": "x",
      "orient": "bottom",
      "gridScale": "y",
      "grid": true,
      "tickCount": {"signal": "ceil(width/40)"},
      "domain": false,
      "labels": false,
      "maxExtent": 0,
      "minExtent": 0,
      "ticks": false,
      "zindex": 0
    },
    {
      "scale": "x",
      "orient": "bottom",
      "grid": false,
      "title": "Average Price ($)",
      "labelFlush": true,
      "labelOverlap": true,
      "tickCount": {"signal": "ceil(width/40)"},
      "zindex": 0
    },
    {
      "scale": "y",
      "orient": "left",
      "grid": false,
      "title": "Manhattan Neighborhood",
      "zindex": 0
    }
  ]
}

We can clearly see some things from the average price per neighborhood, it may take a little reaserch outside just our data, because just going for the cheapest neighborhood in manhattan could put as a ways away from what we want to see and do! Despite thinking that oh Inwood, or Marble Hill is the way to go, that would put us a ways away from the action.

Just for fun, let's take a look at the most expensive area, say we won the lottery and we want to have some fun! Tribeca, the red highlighted bar, is clear and away the most expensive place to stay averaging just about 490$/night.

In my experience when you charge top dollar for a place to stay you should have nothing but raving reviews right? We don't have access to the quality of reviews, but we do have access to the number. Does the price of where you stay have any connection with the number of reviews? (Feel free to zoom in or move around to see what the description says about the place to stay on the chart)

Say we haven't won the lottery, yet. Contrary to popular belief, Harlem is a very up and coming area that is a short train ride away from some awesome attractions downtown. If you use the same central idea as above. We can pick out a place to stay that is in our price range, as well as if that one in our range has some reviews. 


