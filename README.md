# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The purpose of this exercise was to attempt to draw conclusions about the positioning and size of bike-share stations in relation to points of interest in the surrounding area.
The test city in the case was Dublin.
Bike-share station data was provided by citybik.es. Points of interest data was provided by Yelp and FSQ.

## Process
### 1. API connection:
    First an API connection was established with each of the 3 data providers. Once a connection and response was established, sample analysis was completed on the responses to pull out fields of interest and define what manipulation was required for a single bike-share station.
### 2. Scaling:
    The method established in the first step was scaled to apply to all bike stations.
### 3. Join and Summarize:
    The outputs from step 2 were summarized and the merged together to provide a single datbase.
### 4. Analysis and Model Creation:
    Summaries were investigated to establish relationships between variables and a regression model was created to define that relationship.


## Results & Challanges
For both APIs each station returned the max (50) points of interest. Given the variation in the categories returned the scope was narrowed to test the relationship between the volume of pubs and cafes and the size of a bike stations. The rational being that more pubs and cafes suggest a need to serve a higher volume of people and hence a greater need for transportation of the 2 wheeled variety to and from that area. The analysis suggested a weak inverse relationship (corr coef = -0.3) and a linear regression R^2 of 0.1.  

I think the successful application of these APIs is location dependent. When you compare the number of ratings available for FSQ versus Yelp we can see there are far more ratings captured using FSQ. It was also observed for Yelp that when searching for 'restaurants' only 6 unique values were returned. There are more than 6 restaurants in Dublin city centre. This suggests to me that Yelps data is perhaps less 'complete' than FSQ when looking for places in Dublin. Perhaps Yelp is not widely used in Ireland?
What confounds comparing the APIs as well is that they are both limited to 50 responses per request. What this means is that with a broad search we only get a sample of the places in a certain category returned. For example you may get back 5 cafes on one search and 10 the next time you execute it. All this is to say is that the responses for a given category will vary and this will cause inaccuracies in the conclusions made from them.
One potential way around this is to tune the request to look for a single category in the hope of getting a complete sample but unfortunately there was not enough time to completed this. The radius was reduced to 500m to provide a more localised view of the surrounding area. It was observed that there were always 50 points of interest returned. This could be reduced futher in combination with a narrower scope to give a better quality dataset.


## Future Goals
As stated above, if time was not an issue I would refine the API call to reduce the size of the radius and either find a way to remove the response cap or reduce the number of categories requested. I would also look at the bike station density as well. Do we get a higher concentraion of bike station rather than just larger stations?
