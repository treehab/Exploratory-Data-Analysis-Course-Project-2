## Exploratory-Data-Analysis-Course-Project-2

NOTE: My work and answers to the questions are at the bottom of this document.

# Introduction
Fine particulate matter (PM2.5) is an ambient air pollutant for which there is strong evidence that it is harmful to human health. In the United States, the Environmental Protection Agency (EPA) is tasked with setting national ambient air quality standards for fine PM and for tracking the emissions of this pollutant into the atmosphere. Approximatly every 3 years, the EPA releases its database on emissions of PM2.5. This database is known as the National Emissions Inventory (NEI). You can read more information about the NEI at the EPA National Emissions Inventory web site.

For each year and for each type of PM source, the NEI records how many tons of PM2.5 were emitted from that source over the course of the entire year. The data that you will use for this assignment are for 1999, 2002, 2005, and 2008.

# Data
The data for this assignment are available from the course web site as a single zip file:

* Data for Peer Assessment [29Mb]
The zip file contains two files:

PM2.5 Emissions Data (summarySCC_PM25.rds): 
This file contains a data frame with all of the PM2.5 emissions data for 1999, 2002, 2005, and 2008. 
For each year, the table contains number of tons of PM2.5 emitted from a specific type of source for the entire year. Here are the first few rows.

```
##     fips      SCC Pollutant Emissions  type year
## 4  09001 10100401  PM25-PRI    15.714 POINT 1999
## 8  09001 10100404  PM25-PRI   234.178 POINT 1999
## 12 09001 10100501  PM25-PRI     0.128 POINT 1999
## 16 09001 10200401  PM25-PRI     2.036 POINT 1999
## 20 09001 10200504  PM25-PRI     0.388 POINT 1999
## 24 09001 10200602  PM25-PRI     1.490 POINT 1999
```

*fips: A five-digit number (represented as a string) indicating the U.S. county
*SCC: The name of the source as indicated by a digit string (see source code classification table)
*Pollutant: A string indicating the pollutant
*Emissions: Amount of PM2.5 emitted, in tons
*type: The type of source (point, non-point, on-road, or non-road)
*year: The year of emissions recorded

Source Classification Code Table (Source_Classification_Code.rds): 
This table provides a mapping from the SCC digit strings int he Emissions table to the actual name of the PM2.5 source. The sources are categorized in a few different ways from more general to more specific and you may choose to explore whatever categories you think are most useful. For example, source “10100101” is known as “Ext Comb /Electric Gen /Anthracite Coal /Pulverized Coal”.

You can read each of the two files using the readRDS() function in R. For example, reading in each file can be done with the following code:

```
## This first line will likely take a few seconds. Be patient!
NEI <- readRDS("summarySCC_PM25.rds")
SCC <- readRDS("Source_Classification_Code.rds")
```

# Question 1
First we'll aggregate the total PM2.5 emission from all sources for each of the years 1999, 2002, 2005, and 2008.

As we can see from the plot, total emissions have decreased in the US from 1999 to 2008.

![alt text](https://github.com/treehab/Exploratory-Data-Analysis-Course-Project-2/blob/main/plot1.png?raw=true)

# Question 2
First we aggregate total emissions from PM2.5 for Baltimore City, Maryland (fips="24510") from 1999 to 2008.

Overall total emissions from PM2.5 have decreased in Baltimore City, Maryland from 1999 to 2008.

![alt text](https://github.com/treehab/Exploratory-Data-Analysis-Course-Project-2/blob/main/plot2.png?raw=true)

# Question 3

The non-road, nonpoint, on-road source types have all seen decreased emissions overall from 1999-2008 in Baltimore City.
The point source saw a slight increase overall from 1999-2008. Also note that the point source saw a significant increase until 2005 at which point it decreases again by 2008 to just above the starting values.

![alt text](https://github.com/treehab/Exploratory-Data-Analysis-Course-Project-2/blob/main/plot3.png?raw=true)

# Question 4

Emissions from coal combustion related sources have decreased from 6 * 10^6 to below 4 * 10^6 from 1999-2008.

Eg. Emissions from coal combustion related sources have decreased by about 1/3 from 1999-2008!

![alt text](https://github.com/treehab/Exploratory-Data-Analysis-Course-Project-2/blob/main/plot4.png?raw=true)

# Question 5

Emissions from motor vehicle sources have dropped from 1999-2008 in Baltimore City!

![alt text](https://github.com/treehab/Exploratory-Data-Analysis-Course-Project-2/blob/main/plot5.png?raw=true)

# Question 6

Los Angeles County has seen the greatest changes over time in motor vehicle emissions.

![alt text](https://github.com/treehab/Exploratory-Data-Analysis-Course-Project-2/blob/main/plot6.png?raw=true)
