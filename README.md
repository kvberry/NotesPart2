# Notes Part 2: ATSA
#### Kelton Berry

## Class 1: March 9

#### Exam 1
Count up self-examine scores. If over 18 points, recieve check mark. If under 18 points, consider anwering extra problem. 

d
Abstart: a network of autonomous wireless sensor nodes with job of collecting data set up in two field sites in a forested hillsloped region. The goal of this project was to determine the efficacy of wireless sensor networks (WSN) under natural outdoor conditions for collecting high precision environmental data. 


## Class 2: March 11

Must find and remove duplicate packets: potential at multiple hops that duplicates are made.
Original analysis done in R. Ongoing project but data we look at is concentrated in two years. 
Goal is to replicate the graphs of the paper. 

#### Breakout Rooms (Room 2)

Prerequisite: create joint Google colab

Objective 1 for Group: Successfully read in the data. 

How to we remove duplicates?
* compare enteries within a set timeframe and remove exact duplicate
* could use a for loop to compare every data point to every other data point and delete the duplicates (must compare every value)
* must narrow the time range (+ or - 15 min or hour) --> can't be all of time as replicates are inventibale 
* Agreed upon 15 min range (most accurate?)

Creating a loop to create list of nodes

Must also filter out invalid values: those affected my moisture, etc

## Class 3: March 16:

#### Breakout Rooms (Room 2)

Before removing duplicates should remove invalid values
* convert the measurements and then determine if in range to be valid

difftime() function within R
* only looks for points after the current point
* keeps last of duplicate group
* only look at time intervals after 15 minutes
* remove all the values until 14 minutes and then after 14 minutes check to see if duplicates


Where does implementation of Pearl Code go: goes in last?


## Class 4: March 18

#### Case Study 2: FLUXNET Data

FLUXNET is a collection of observation towers that measure fluxes between the Earth's surface and the atmosphere. These towers are found all over the world. 
However, extensive gaps in the the data (due to malfunctions, errors, interuptions, etc.). Therefore, we need to fill this missing data points with a gapfilling technique. 


#### Breakout Room 2
The group decided the best approach was to do individual work to complete excercise 2.1


## Class 5: March 23

Case Study 2: Solar radition
 * use to predict plant response/production

There are gaps in time series, need to fill in gaps. 
* look to physical model, i.e. solar radition (dependment on time)

𝐼𝑜 represents radiation of sun on specific location on earth

Challenge: finidng half hour 𝐼𝑜 values
  *  Can find by the following components:
        -* olar constant, distance factor and inclination factor

Simple Process-Led Algorithms for Simulating Habitats (SPLASH) mode:
* this is a way for the team to fill in missing data
* included within the code is various R functions 
* Solar R: julian_day, dsin, dcos, calc_daily_solar, berger_ts
    * julian_day: helps us find the day of year n
    * calc_daily_solar: requires constants, input: latitude; day of the year; elevation, year, fraction of sunshine days and daily average air temp (optional)
    * berger_ts: calculates true anomalies and true longitude
    * distance factor via the berger method
    * calculate declination angle (delta)
    * calculate sunset hour angle
    * calculate daily extraterrestrial radiation


## Class 6: March 25

Ouput of calc_daily_solar is ra_j.m2. This represents daily solar radiation in joules/sq meter. 

However, we still have the problem of being unable to find 𝐼𝑜 
  * Can do this by replacing sunset hour angle with the hour angle
  * This can be helped by code of GePiSaT

GePiSaT: in its solar.py file has solution for converting half-hour estimate  
  * need to convert this into R code
  * can help us gap-fill


## Class 7: March 30

Dealing with outliers

Peirce's criterion:
* a form of removing outliers, that rejects doubtful observations
* Pierce's criterion works by removing points outside of the max deviation expected from our data
* The deviation is based upon the squared error, i.e. squared residuals

For Lab 2 work to remove outliers from FLUXNET data by using Peirce's criterion:
  * Spefically remove outliers from the linear relationship between incoming shortwave radiation (SW_IN_F) and Net Ecosystem exchange
  * mean squared error be multilpied by peirces criterion, this is the threshold for outliers (ie points greater than this are outliers)


## Class 8: April 1

Today the class comprised of working on our labs in breakout rooms. 

