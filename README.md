# Notes Part 2: ATSA
#### Kelton Berry

## Class 1: March 9

#### Exam 1
Count up self-examine scores. If over 18 points, recieve check mark. If under 18 points, consider anwering extra problem. 

#### Case Study 1 of Part 2
Abstart: a network of autonomous wireless sensor nodes with job of collecting data set up in two field sites in a forested hillsloped region. The goal of this project was to determine the efficacy of wireless sensor networks (WSN) under natural outdoor conditions for collecting high precision environmental data. 


## Class 2: March 11

Must find and remove duplicate packets- potential at mutiple hops that duplicates are made.
Original analysis done in R. Ongoing project but data we look at is concentrated in two years. 
Goal is to replicate the graphs of the paper. 

#### Breakout Rooms (Room 2)

Pre-Recs: create joint Google colab

Objective 1: Successfully read in the data. 

How to remove duplicates:
-compare enteries within a set timeframe and remove exact duplicate
-we could use a for loop to compare every data point to every other data point and delete the duplicates (must compare every value)
-must narrow the time range (+ or - 15 min or hour) --> can't be all time as replicates are inventibale 
-Agreed upon 15 min range (most accurate?)

-Creating a loop to create list of nodes


Must filter out invalid values: those affected my moisture, etc

## Class 3: March 16:

#### Breakout Rooms (Room 2)

Before removing duplicates should remove invalid values

-convert the measurements and then determine if in range to be valid

difftime() function within R
-only looks for points after the current point
-keeps last of duplicate group
-only look at time intervals after 15 minutes
-remove all the values until 14 minutes and then after 14 minutes check to see if duplicates



Implementation of Pearl Code: goes in last?


## Class 4: March 18

#### Breakout Room 2



## Class 5: March 23

Case Study 2: Solar radition
-use to predict plant response/production

There are gaps in time series, need to fill in gaps. 
-look to physical model, ie solar radition (dependment on time)

𝐼𝑜 represents radiation of sun on specific location on earth

Challenge: finidng half hour 𝐼𝑜 values
  - Can find by the following components:
        -solar constant, distance factor and inclination factor



SPLASH: look at Section 2.3 -same equation as in notebook




## Class 6: March 25

Get day of the year by the julian function 
