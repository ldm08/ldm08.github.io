---
title:  "Shopping for Airbnbs at the Mall?"
description: "Exploring Washington D.C. using Airbnb data" 
author: Lawrence Dugom
classes: wide
author_profile: true
header:
  image: /images/dc.jpeg
---


---

# Background
Now with 7 million current listings, "accessible in 62 languages across 220+ countries and regions", Airbnb has been gaining popularity since its start in 2008. It is the Uber of the hospitality industry, allowing property owners to list their space and take full control of pricing.
Part of the Inside Airbnb project, Airbnb offers data for cities all over the world. I decided to choose Washington D.C. due to its history, art, culture, and attractions for every type of visitor. Made available to me were review, listing, and host data.
The aim of this post is to delve into the Washington D.C. Airbnb market to find out more about the types of listings, the kind of hosts running businesses, and the reviews Airbnb-ers leave from their experiences. Now, let's see what we find.


---

# Part I: Properties & Pricing
 
 <img src="/images/table1.png">

For the bottom 95% of listings, we see neighborhood averages range from $83 to $186. Among the 39 neighborhoods in the listings data, Georgetown, Southwest/Waterfront, and Spring Valley are the most expensive.
While remaining within the top 10 most expensive neighborhoods, you can still save an upwards of $50–100/night by choosing a less expensive offering in a local neighborhood. When comparing the 10 most expensive neighborhoods to the 10 most affordable neighborhoods, you can potentially save double by choosing an average-priced Airbnb out of the lower-priced tier of neighborhoods.
The table reveals that 9 of the 10 most expensive neighborhoods also have the biggest interquartile ranges, which means you can still find a reasonably priced listing in an expensive area. With higher-priced neighborhoods having wider price ranges, the potential exists for an affordable Airbnb in an upscale neighborhood.


## How expensive are the top 25% of listings?

The top quartile of prices start around $200 and climb all the way up to a whopping $10,000. In regards to bedroom count, we see the priciest options are not necessarily the largest.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~lawrencedugom/10.embed"></iframe>


## Does proximity to attractions play a factor in the listing price?

<iframe width="900" height="800" frameborder="1" scrolling="no" src="//plotly.com/~lawrencedugom/16.embed"></iframe>

After I split the listing data into 10 equally-distributed bins based on price, I saw that more expensive listings appeared to be closer to the National Mall area and Downtown. Though there are higher priced listings sprinkled in the cheaper areas away from the bottom center of the map, it looks like the majority of mid-to-upper priced tiers form a crescent around D.C.

 <img src="/images/dc map.png">

But does proximity to attractions play a role in listing price? To answer this question, I calculated the distance to both the Washington Monument and Capitol One Arena from each one of the listings, two major attractions in both the National Mall and Downtown area. I saw no linear relationship after looking at the correlation between distance and price. On the other hand, I did notice slightly greater positive associations between distance to the monument and the three attributes: bedrooms, 30-day availability, and the lowest priced decile of listings (0-$53). With this information, it seems as though cheaper, more available, higher bedroom count listings tend to be farther away from the monument. Moreover, there also were weak negative correlations between distance to the monument and both location review scores and host listing count.
Location is key for listing price at a neighborhood level. Like other larger cities, there is not only one place to be in D.C. You can find a popular, high priced listing in Georgetown as well as Southwest on the opposite side of town. The crescent around the center of D.C. seems to show there are multiple areas in demand, but what do these listings have in common?

## Are there common property types, room types, bedroom, and bathroom counts?

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~lawrencedugom/18.embed"></iframe>

At the property level, apartments, houses, and townhouses form the biggest share of property types in the listings, 44%, 20%, and 15% respectively. As far as room types, entire homes/apartments form the majority at 71%, while 25% are private rooms. In the graph (sized by the number of beds) below, we can see that some of the shared rooms and hotels have many beds available. The most common number of bedrooms and bathrooms is overall is one each.


# Part II: Hosts

 <i>"Hosts with multiple listings are more likely to be running a business" - Airbnb</i>

<p>After noticing that around 46% percent of the Washington D.C. hosts had multiple listings, I was curious if there were distinguishable characteristics of these hosts. Do they individually tend to be in certain neighborhoods? Do they stick to certain price points? Do their reviews tend to be better?</p>

## Do hosts with multiple listings tend to be in certain neighborhoods?
Approximately 77% of the hosts with multiple listings only list in one neighborhood. The other ambitious 23% of the hosts are focused on popular neighborhoods such as DuPont Circle, Shaw, Downtown, Capitol Hill, West End, and Union Station. Hosts with multiple listings appear to be following the overall trend as far as which neighborhood they choose to list in.

 <img src="/images/hosts 1.png">

## Do they stick to certain price points?
To answer this question, I mostly studied the difference between the 75th and 25th percentile for these hosts' listings (interquartile range). I found out that the average IQR was around $40, and that the median IQR was $25.

## Can we expect better reviews?
After doing a weighted average of the various review dimensions (overall rating, accuracy, cleanliness, check-in, communication, location, value) using the number reviews each of the listings received every month, the overall rating averaged out to be 95 out of 100 where the rest of the dimensions averaged 9.5 out of 10 or greater. I saw that even hosts without multiple listings also had very high ratings as well. This led me to explore the dataset for reviews Airbnb provides.


# Part III: Reviews


The review score ratings in the listings data generally had high scores, so I used the reviews data. With over 350,000 review comments going back to 2009, I used this opportunity to find out if certain neighborhoods or price ranges revealed any patterns in the reviewer sentiment.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~lawrencedugom/26.embed"></iframe>

The results above reflect the standard deviation of the normalized, weighted compound scores (ranging from -1 to 1) that the sentiment analysis library I used yielded. With this information, we can now evaluate risk when deciding between neighborhoods to stay in by looking at the spread of sentiment. Neighborhoods south of the Anacostia River (bottom right of map) seem to generally have higher dispersion in their sentiment scores, while neighborhoods in the northeastern part of D.C. have lower dispersion.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~lawrencedugom/24.embed"></iframe>

This next map is similar to the previous, however, neighborhoods colored by the mean of their sentiment scores. It looks like neighborhoods in south D.C. like River Terrace and Historic Anacostia (bottom right) have more spread in their scores and also are on average lower relative to areas such as Georgetown, DuPont Circle, and West End (upper left of map). One thing to keep in mind is that overall the sentiment in the reviews across all neighborhoods is very good, with 25th percentiles never going below .64.
As far as sentiment revealing anything interesting in pricing, I saw no pattern between prices and overall sentiment score, with a correlation close to zero. After a look at the listing price deciles, I also saw no difference in sentiment scores, all hovering around .8, with the bottom buckets ($0-$53 and $53-$71 ) seeing average scores of .76 and .72 respectively.


# Conclusion


Opening up the Airbnb data allowed me to figure out a lot about the Washington D.C. market. Let's summarize some of the key discoveries we made:

 1) Neighborhoods in D.C. have average listings anywhere from $83-$186/night (excluding top 5% of listings), with the top 25% of listings ranging from $200-$10,000.

 2) The most common property type is apartments, followed by houses, and then townhouses, while the most common floor plan is a 1 bed x 1 bath.

 3) Almost half of the listings are owned by hosts with multiple properties, and these owners tend to list at small price ranges and if they own many listings, stick to the most popular neighborhoods.

 4) Neighborhoods in South D.C. have lower overall sentiment scores on average and greater spread as well. On the other hand, Northwest D.C. has higher concentrations of neighborhoods such as Georgetown and DuPont Circle, where the sentiment scores from the reviews data reveal higher sentiment and lower spread.

Hopefully, this post provided some perspective on the types of listings and their prices, how Airbnb hosts run their businesses, as well as the sentiment of the guests' experiences.


To see more about the analysis, view my GitHub here.