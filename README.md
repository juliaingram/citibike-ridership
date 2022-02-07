# Analyzing Citi Bike Ridership during the Pandemic

[Read the story on my portfolio site](http://juliaingram.github.io/citibike)

## Goal
This project aimed to analyze data on how Citi Bike ridership changed over the course of the COVID-19 pandemic. It uses data published by Citi Bike on monthly ridership data. Each row in the datasets published by the rideshare company contains data on one ride, including where and when it started and ended. 

## Findings
Compared with the MTA, Citi Bike is soaring above pre-pandemic levels. Citi Bike ridership grew 58% between 2018 and 2021, and with that growth came a shift away from commuting, the data suggests. Citi Bikers are using the service less often during the morning rush, with many pre-pandemic rides occuring between 8 and 9 a.m., but rides during 2020 and 2021 more evenly distributed throughout daytime hours. Ridership still peaks between 5 and 7 p.m.

The percentage of Citi Bike rides done by casual riders vs. those who pay the annual membership fee has increased by 19%, further indicating that Citi Bike ridership is shifting away from regular commuters and more recreational trips.

Lastly, the analysis showed that the top spots to start and stop a ride are more scattered throughout Manahattan, whereas before they were clustered in Midtown.

## Data Source
I downloaded monthly data from [Citi Bike's website](https://ride.citibikenyc.com/system-data). I downloaded data from January 2018 to December 2021, unzipped the files and read them into a Jupyter notebook, combining the data to create a dataframe for each year. 

To compare with MTA ridership, I downloaded the single CSV containing daily ridership data throughout the pandemic from the [MTA's website](https://new.mta.info/coronavirus/ridership).

## Analysis

[My Jupyter notebook](Citi%20Bike%20Analysis.ipynb) contains an anotated analysis. 

After reading in the data and separating it into a dataframe for each year, I resampled the data by hour and calculated the percent of the day the rides that occured during that hour took up. I plotted the results using plotnine. This helped me identify shifts in Citi Bike rush hour. To quantify overall growth, I was able to simply calculate the percent change in the length of the dataframe for 2018 and the dataframe for 2021 because each row represents a ride. 

To compare with MTA Subway ridership, I loaded in the MTA daily ridership data. To equalize between the Subway and Citi Bike, since the Subway has a much greater overall ridership, I calculated ridership in terms of percent of pre-pandemic levels for Citi Bike. I did this by using the 2019 monthly total rides data. Percent of pre-pandemic levels for the MTA was already included in the daily data, so I took the median for each month.  

For geographic analysis of Citi Bike ridership throughout the day, I reformatted the data by grouping each annual dataframe by latitude and longitude coordinates as well as the hour it occurred in, then extracting the top 10 most popular stations per hour. I pulled together the top 10 for each hour for each year into a single dataframe that I transformed into an animated map using Tableau. 

## New skills & growth

This project uses Python and pandas to manipulate and analyze data. Combined, the four years of data are over 84 million rows, so I learned how to optimize my functions, queries and data structures to expedite the analysis and reduce the burden on my computer. I learned plotnine shortly before beginning this project, and this was my first time putting it in action on a real-world dataset (rather than one built-in to the plotnine package). I also pushed the limits of my Tableau skills by creating an animated map. 

## Further expansion

Currently, the Tableau sheets are not embedded in the website and instead recordings of the animation are embedded. If the visualizations were embedded, the user would be able to stop and start the animation on the hour of their choosing and hover over each point to view the name of the station and the exact number of rides.

There's also room for further analysis on Citi Bike usage on the weekends vs. weekdays to further examine the use of Citi Bike for commuting. With more time, this analysis could be extended to include a year-over-year comparison of weekday and weekend trips. 
