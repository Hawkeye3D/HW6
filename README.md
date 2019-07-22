# HW6
Homework for week 6 of RiceCamp
## HW 





## THESIS EVALUATION

After spending several hours evaluating this assignment, I concluded that it is not a good approach to the problem, either programmatically or theoretically.  One can assume that the suggested solution could have been put forth by a manager who had not studied the problem as deeply as a programmer would.  From a theoretical standpoint, randomizing 500 lats and longs and then finding the nearest city to reference is hugely flawed.  Two thirds of the Earth is covered by water and that means that two thirds of the randomized hits will be in the ocean.  Since the Citipy has a nearest point function,and is used to find the nearest city, that means the data will be heavily biased towards coastal cities, and scattered islands in the oceans.  Use of the Citipy data is not a good choice, so I have abandoned it.  

**My Thesis**
If we could get the weather information from the randomized lats and long positions it would be more representative.  But we can only use points where  measurements are made.  Openweather.org is a very comprehensive, structured, and maintained API, and one of the things they provide, free of charge is bulk data, with all of the weather measurement locations in JSON file structures.  Now, comes the power of Pandas, and JSON.  I can download the data file and read it into a JSON file, then read that into a Dataframe.  There are over 200,000 points of measurement; I can then randomly select a list of cities with:

```Python
 df = df.sample(510) #(I over sample by three sigma the error rate)
```

and query the openweathermaps.org with that data to build up my analysis.  I am essentially assured that the location exists (using the *current.city.list.json* it is about 99.8%), but I am not assured that there is data associated with the station, or that the measurement station is still active, since the file is from a few years ago) Then I plot it out.

Depending upon how time consuming it is to query 500 cities from Openweathermap, I can continue my investigation by doing more samples, and varying the sample size to determine how skewed the analysis would be if I used, say, 50 samples, then 200 and so on.  I purchased a monthly license so I can play games with it.(Freebees are limited to 60 per minute, which they ignore for a while, until they don't. The smart way around it is to put the labored dataset into a file, and use that as a basis for testing)

**Conclusions**
The notion that the temperature increases towards the equator is false. The temperature his highest in the areas where the sun is directly overhead, and that varies constantly.  Not finished...
