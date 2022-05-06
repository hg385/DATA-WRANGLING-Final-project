<h1 align="center">:taxi: NYC-Taxi :taxi:</h1>
<p align="center">
<img src= "https://user-images.githubusercontent.com/74512335/138792965-4a9225f1-09fc-4479-8dac-355f87af8f6f.png" />
</p>

**Link to dataset: https://maven-datasets.s3.amazonaws.com/Taxi+Trips/NYC_Taxi_Trips.zip**

## About the dataset
- This dataset contains 6 tables in csv format, along with a geospatial map in TopoJSON and Shapefile formats
- The 4 Taxi Trips tables contain a total of 28 million Green Taxi trips in New York City from 2017 to 2020. 
- Each record represents one trip, with fields containing details about the pick-up/drop-off times and locations, distances, fares, passengers, and more
- The Taxi Zones table contains information about 265 zone locations in New York City, including the location id, borough, and service zone
- The Taxi Zones Map files contain a map of New York City with divisions for the 265 locations that can be used to create custom map visuals in Power BI (TopoJSON) or Tableau (Shapefile)

## Cleaning Steps
- Let’s stick to trips that were NOT sent via “store and forward”
- I’m only interested in street-hailed trips paid by card or cash, with a standard rate
- We can remove any trips with dates before 2017 or after 2020, along with any trips with pickups or drop-offs into unknown zones
- Let’s assume any trips with no recorded passengers had 1 passenger
- If a pickup date/time is AFTER the drop-off date/time, let’s swap them
- We can remove trips lasting longer than a day, and any trips which show both a distance and fare amount of 0
- If you notice any records where the fare, taxes, and surcharges are ALL negative, please make them positive

## Analysis Steps
- What's the average number of trips we can expect this week?
- What's the average fare per trip we expect to collect?
- What's the average distance traveled per trip?
- Which days of the week and times of the day will be busiest?
- What will likely be the most popular pick-up and drop-off locations?
