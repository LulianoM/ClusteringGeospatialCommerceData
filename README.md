# Capstone Project - The Battle of the Neighborhoods ( BRAZIL VERSION )
### Applied Data Science Capstone by IBM/Coursera

## Table of contents
* [Introduction: Business Problem](#introduction)
* [Data](#data)
* [Methodology](#methodology)
* [Results and Discussion](#results)
* [Conclusion](#conclusion)

## Introduction: Business Problem <a name="introduction"></a>

In this project, we will try to find an ideal place for a restaurant. Specifically, this report will be directed to interested parties interested in opening a ** izzeria** in **Madureira**, Rio de Janeiro, Brazil.

As there are many restaurants in Rio, we will try to detect **places that are not yet full of restaurants**. We are also particularly interested in **reas without pizzerias nearby**. We would also prefer locations **as close as possible to the chosen center**, assuming the first two conditions are met.

We will use our data science powers to generate some more promising neighborhoods based on these criteria. The advantages of each area will then be clearly expressed so that the best possible final location can be chosen by the interested parties.

## Data <a name="data"></a>

Based on the definition of our problem, the factors that will influence our decision are:
* number of restaurants in the neighborhood (any type of restaurant)
* number and distance of pizzerias in the neighborhood, if any
* distance from the neighborhood to the center

We decided to use a grid of places with regular spacing, centered in the center of the city, to define our neighborhoods.

The following data sources will be needed to extract / generate the necessary information:
* candidate area centers will be generated algorithmically and approximate addresses of centers in those areas will be obtained using **reverse geocoding from the Google Maps API**
* number of restaurants and their type and location in each neighborhood will be obtained using the **Foursquare API**
* the coordinate of the center of Madureira will be obtained using **geocoding from the Google Maps API**

## Methodology <a name="methodology"></a>

In this project, we will direct our efforts to detect areas of Madureira with low density of restaurants, mainly those with low number of pizzerias. We will limit our analysis to an area of ​​approximately 6 km around the city center.

In the first stage, we collected the **necessary data: location and type (category) of each restaurant 6 km from the center of Madureira**. We also **identified pizzerias** (according to Foursquare categorization).


The second step in our analysis will be the calculation and exploration of '**restaurant density** 'in different areas of Madureira- we will use **heat maps** to identify some promising areas near the center with a low number of restaurants in general (* and * no pizzeria nearby) and focus our attention on these areas.


## Results and Discussion <a name="results"></a>

Our analysis shows that, although there are a large number of restaurants in Madureira, there are low density pockets of restaurants very close to the city center. The highest concentration of restaurants was detected in the north, so we focused our attention on the south, southeast and east areas, corresponding to the Campino and Cascadura neighborhoods.
After directing our attention to this narrowest area of ​​interest, we first created a dense grid of candidates for locations (spaced 100 m apart); these locations were filtered so that those with more than two restaurants within a 250m radius and those with an Pizza restaurant closer to 400m were removed.



These site candidates were then grouped together to create zones of interest that contain the largest number of site candidates. Center addresses in these zones were also generated using reverse geocoding to be used as markers / starting points for more detailed local analyzes based on other factors.

The result of all of this is 10 zones containing the largest number of potential new restaurants based on the number and distance from existing locations - both restaurants in general and pizza restaurants in particular. This, of course, does not mean that these areas are, in fact, ideal places for a new restaurant! The purpose of this analysis was to provide information only about areas close to the center of Madureira, but not crowded with existing restaurants (especially pizza) - it is perfectly possible that there is a very good reason for the small number of restaurants in any of these areas, reasons that would make them unsuitable for a new restaurant, regardless of the lack of competition in the area. The recommended zones should therefore only be considered as a starting point for a more detailed analysis that could eventually result in a location that not only has no competition nearby, but also other factors taken into account and all other relevant conditions met. .

## Conclusion <a name="conclusion"></a>

The objective of this project was to identify areas of Madureira close to the center with a low number of restaurants (especially pizza restaurants), in order to help interested parties to narrow the search for the ideal location for a new pizzeria. When calculating the distribution of the density of the restaurant from Foursquare data, we first identify general neighborhoods that warrant further analysis and then generate an extensive collection of locations that satisfy some basic requirements relating to restaurants in the vicinity. The grouping of these sites was then carried out in order to create the main zones of interest (containing the largest number of potential sites) and the addresses of these zone centers were created to be used as starting points for the final exploration by the interested parties .

The final decision on the ideal location of the restaurant will be made by the stakeholders based on the specific characteristics of the neighborhoods and locations in each recommended area, taking into account additional factors such as the attractiveness of each location (proximity to the park or water), noise levels / proximity to main roads, real estate availability, prices, social and economic dynamics of each neighborhood, etc.



In the third and final stage, we will focus on the most promising areas and, within them, we will create ** groups of locations that meet some basic requirements ** established in discussion with stakeholders: we will consider locations with **a maximum of two restaurants within 250 meters**, and we want locations **without pizzerias within 400 meters**. We will present the map of all these locations, but we will also create clusters (using **k-means clustering**) of these locations to identify zones / neighborhoods / general addresses that should be a starting point for the final exploration of the 'street level' and search for the ideal location of the location by the interested parties.

