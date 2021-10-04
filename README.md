# Machine-Test
Test tasks
--------------------------
Task : 1 , File : Lat_Long.ipynb

Find the lat_long points which are no in continous path.

import pandas -- to store the csv file in dataframe
import matplotlib.pyplot  -- to visualise the points in 2-D space
import numpy -- to get the measures of central tendency

STEPS :

1 . loaded the lat_long csv file to pandas dataframe
2.  Split the lat and long columns to individual list
3.  Counted the total number of points to find concurrent points.
4.  Annotated the points with cordinates to find the point which is not in continous path with rest of the points.

Task : 2 , File : DBQuery_Final.ipynb

From the given terrain list with kilometeres, write a python script to generate DB of each
latitude and longitude pair with matching terrain information, Write Query to list all the points with terrain “road” in it without “civil station”

import pandas as pd -- to store and work with datas
import sqlite3 -- database

STEPS: 

1. loaded lat_long.csv and terrain.csv to separate dataframes ,data1 & data2
2. Repeated tearrain.csv rows using pandas append() method to create new dataframe, newdata2
3. concatenated data1 and newdata2 using pandas concat() method to create a new dataframe , concatenated
4. Created sqlite TEST.DB, created table TEST and inserted concatenated dataframe.
5. Qureied out lat_long points contatiningn “road” in it without “civil station” using the query 
   "SELECT latitude,longitude,terrain FROM TEST WHERE ',' || terrain || ',' LIKE '%,' || 'road' || ',%'  OR ',' || terrain || ',' LIKE '%,' || 'boundary wall' || ',% ' AND ',' || terrain || ',' NOT LIKE '%,' || 'civil station' || ',%'
   
6. Executed the query and stored the result in query_result.csv

