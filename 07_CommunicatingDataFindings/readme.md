# Ford Go Bike 2018 Exploration
`by Theresa Kocher`

## Dataset

This document explores a dataset containing rent information of the bike rental agency of Ford. To avoid long computation times only the acquired data of the year 2018 are analysed. There are 1863721 rows in the data set. The data can be downloaded [here](https://www.fordgobike.com/system-data),


## Summary of Findings

In the exploration, I found that 11771 rows had missing station id and name, although the latitude and longitude were given of start and end station. Thus, I filled up these missing values with the station id and name of the closest station (computed with the euclidean distance to all of the stations with existing name and id). There were other missings in the members variables birth year and gender. Most of them were found in users of type customer. Which is obvious, since they may not use the rent service that often than subscribers. But also some subscriber didn't filled their gender and birth year attributes.

Also the rush hours inbetween 7 and 10 o'clock and between 16 and 19 o'clock are clearly visible in the data. More users rent a bike at this times. And May to October are the most active months. Additionally, the exploration shows, that the most rents are for a duration of 3-15 minutes.


There are about 20 more busier rent stations than the others. This could be computed by their amount of rents overall. A new feature was added with a busy stage, by including 3 different levels of rent amounts. Then the busiest stations were plotted on a map. Most of the busiest stations are located in San Francisco. 3 medium busy stations are also located in San Bay and one in San Jose.

The locations of the rent stations are in 3 different cities: San Francisco, San José and East Bay. With the nearest neighbour algorithm the 3 clusters of the rent station locations could be extracted. Then they were added as new features to the rent stations and rent activities. This is how an analysis of the member's age and gender distribution of all cities in comparison could be made.

The insights of the user differences inbetween the 3 cities were interesting. In San Francisco and San Jose are only ablout 1/5 female users and 4/5 male and a view of other gender. In San Bay were also less female then male but there were 1/3 female and 2/3 male. The average age was lowest in San Jose with 30 years. Whereas it was 35 years in San Francisco and 34 years in East Bay. There were no significant differences in duration time inbetween all three cities. In general, there were the most uses (rents) in San Francisco.



## Key Insights for Presentation

For the presentation, I focus on the different locations of rent stations, their busy stage and the comparison of their user attributes. Therefore, I show the different amount of rents per stations and the busy stage extraction. Also, I will show the clustering of the 3 station's centers to continue with the comparison of the member's attributes in all 3 cities.


## Feedback from others

- Remove data of 2019, because it distorted the month distribution.
- Categorize the busy range for easier interpretations in the map.
- Change color for busy range color (darker/more red for more stressed/busier stations).
- Some missing axis descriptions.



## References

Ford GoBike data from: https://www.fordgobike.com/system-data

Euclidean distance computation (used for the closest rent station to fix missing station name and id) from: https://stackoverflow.com/questions/41336756/find-the-closest-latitude-and-longitude

Basemap example to plot longitude and latitude data: https://jakevdp.github.io/PythonDataScienceHandbook/04.13-geographic-data-with-basemap.html

K-means algorithm from: https://mubaris.com/posts/kmeans-clustering/