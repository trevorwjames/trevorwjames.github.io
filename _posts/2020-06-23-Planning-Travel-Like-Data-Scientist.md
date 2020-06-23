---
layout: post
title: Traveling Like a Data Scientist
subtitle: Using AirBnB Data to make decisions on where to stay
cover-img: /assets/img/manhattanskyline.jpeg
tags: [travel, airbnb, NYC]
---

## Finding a place to stay in New York City can be stressful...

Rather than relying on the pictures, the wordy descriptions, and the fluffy stuff. Let's let the data decide what AirBnB we should select for our journey to the big apple. 

When you have the job of reserving a room for your trip, there are so many different options to take into consideration. Price, location, reviews, looks, host, etc. what we have done here is take a small portion of the objectivity out of it and look to understand our options base upon the Data!
Despite Manhattan being just under 23 square miles, there are 33 different unique "neighborhoods" that AirBnB uses to identify the area in which the reservation is located in. I thought in order to make it a little easier to search for prices I would look at the average price per neighborhood. This would make it a little easier to search if I could filter down to the neighborhoods that had a reasonable price range. (see chart of average per neighborhood)

<iframe>
<html>
<head>
  <style>
    .error {
        color: red;
    }
  </style>
  <script type="text/javascript" src="https://cdn.jsdelivr.net/npm//vega@5"></script>
  <script type="text/javascript" src="https://cdn.jsdelivr.net/npm//vega-lite@4.8.1"></script>
  <script type="text/javascript" src="https://cdn.jsdelivr.net/npm//vega-embed@6"></script>
</head>
<body>
  <div id="vis"></div>
  <script>
    (function(vegaEmbed) {
      var spec = {"config": {"view": {"continuousWidth": 400, "continuousHeight": 300}}, "layer": [{"mark": "bar", "encoding": {"color": {"condition": {"value": "red", "test": "(datum.neighborhood === 'Tribeca')"}, "value": "blue"}, "x": {"type": "quantitative", "axis": {"title": "Average Price ($)"}, "field": "avg_price"}, "y": {"type": "nominal", "axis": {"title": "Manhattan Neighborhood"}, "field": "neighborhood"}}, "title": "Average AirBnB Price per night for different Neighborhoods in Manhattan"}, {"mark": {"type": "text", "align": "left", "baseline": "middle", "dx": 3}, "encoding": {"color": {"condition": {"value": "red", "test": "(datum.neighborhood === 'Tribeca')"}, "value": "blue"}, "text": {"type": "quantitative", "field": "avg_price"}, "x": {"type": "quantitative", "axis": {"title": "Average Price ($)"}, "field": "avg_price"}, "y": {"type": "nominal", "axis": {"title": "Manhattan Neighborhood"}, "field": "neighborhood"}}, "title": "Average AirBnB Price per night for different Neighborhoods in Manhattan"}], "data": {"name": "data-ff08b1bfe8d2846933cf4fe11db1a68e"}, "$schema": "https://vega.github.io/schema/vega-lite/v4.8.1.json", "datasets": {"data-ff08b1bfe8d2846933cf4fe11db1a68e": [{"neighborhood": "Midtown", "avg_price": 282.7}, {"neighborhood": "Harlem", "avg_price": 119.0}, {"neighborhood": "East Harlem", "avg_price": 133.2}, {"neighborhood": "Murray Hill", "avg_price": 221.0}, {"neighborhood": "Hell's Kitchen", "avg_price": 204.8}, {"neighborhood": "Upper West Side", "avg_price": 210.9}, {"neighborhood": "Chinatown", "avg_price": 161.5}, {"neighborhood": "West Village", "avg_price": 267.7}, {"neighborhood": "Chelsea", "avg_price": 249.7}, {"neighborhood": "Inwood", "avg_price": 88.9}, {"neighborhood": "East Village", "avg_price": 186.1}, {"neighborhood": "Lower East Side", "avg_price": 186.3}, {"neighborhood": "Kips Bay", "avg_price": 202.4}, {"neighborhood": "SoHo", "avg_price": 287.1}, {"neighborhood": "Upper East Side", "avg_price": 188.9}, {"neighborhood": "Washington Heights", "avg_price": 89.6}, {"neighborhood": "Financial District", "avg_price": 225.5}, {"neighborhood": "Morningside Heights", "avg_price": 114.8}, {"neighborhood": "NoHo", "avg_price": 295.7}, {"neighborhood": "Flatiron District", "avg_price": 341.9}, {"neighborhood": "Roosevelt Island", "avg_price": 113.3}, {"neighborhood": "Greenwich Village", "avg_price": 263.4}, {"neighborhood": "Little Italy", "avg_price": 222.1}, {"neighborhood": "Two Bridges", "avg_price": 127.1}, {"neighborhood": "Nolita", "avg_price": 230.1}, {"neighborhood": "Gramercy", "avg_price": 222.8}, {"neighborhood": "Theater District", "avg_price": 248.0}, {"neighborhood": "Tribeca", "avg_price": 490.6}, {"neighborhood": "Battery Park City", "avg_price": 367.6}, {"neighborhood": "Civic Center", "avg_price": 191.9}, {"neighborhood": "Stuyvesant Town", "avg_price": 169.1}, {"neighborhood": "Marble Hill", "avg_price": 89.2}]}};
      var embedOpt = {"mode": "vega-lite"};

      function showError(el, error){
          el.innerHTML = ('<div class="error" style="color:red;">'
                          + '<p>JavaScript Error: ' + error.message + '</p>'
                          + "<p>This usually means there's a typo in your chart specification. "
                          + "See the javascript console for the full traceback.</p>"
                          + '</div>');
          throw error;
      }
      const el = document.getElementById('vis');
      vegaEmbed("#vis", spec, embedOpt)
        .catch(error => showError(el, error));
    })(vegaEmbed);

  </script>
</body>
</html>
</iframe>

We can clearly see some things from the average price per neighborhood, it may take a little reaserch outside just our data, because just going for the cheapest neighborhood in manhattan could put as a ways away from what we want to see and do! Despite thinking that oh Inwood, or Marble Hill is the way to go, that would put us a ways away from the action.

Just for fun, let's take a look at the most expensive area, say we won the lottery and we want to have some fun! Tribeca, the red highlighted bar, is clear and away the most expensive place to stay averaging just about 490$/night.

<iframe>

</iframe>

In my experience when you charge top dollar for a place to stay you should have nothing but raving reviews right? We don't have access to the quality of reviews, but we do have access to the number. Does the price of where you stay have any connection with the number of reviews? (Feel free to zoom in or move around to see what the description says about the place to stay on the chart)

Say we haven't won the lottery, yet. Contrary to popular belief, Harlem is a very up and coming area that is a short train ride away from some awesome attractions downtown. If you use the same central idea as above. We can pick out a place to stay that is in our price range, as well as if that one in our range has some reviews. 


