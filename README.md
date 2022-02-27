# SQLAlchemy-Challenge
Climate analysis and exploration - Honolulu Hawaii.


## Bring in dependencies
    ### Matplotlib, Pandas, Datetime
    - %matplotlib inline
    - from matplotlib import style
    - style.use('fivethirtyeight')
    - import matplotlib.pyplot as plt
    - import numpy as np
    - import pandas as pd
    - import datetime as dt

    ### Python SQL toolkit and Object Relational Mapper
    - import sqlalchemy
    - from sqlalchemy.ext.automap import automap_base
    - from sqlalchemy.orm import Session
    - from sqlalchemy import create_engine, func, inspect

    ### import Flask
    - from flask import Flask

## create engine to enable connection to hawaii.sqlite
    - leverage base automap and base.classes to reflect on database

# Precipitation Analysis
## use inspect to assess table structure

## save classes as references

## create plot trending precipitation by date
    - use session query to pull all records
    - convert to DataFrame
    - calculate most recent date and use strptime to allow query

    ![](/Images/MostRecentDate.png)

    - calculate date 12 months prior to most recent date
    - use session query to grab observations with time frame set by most recent date and start date
    - set date as index
    - plot trend using precipitation against date

    ![](/Images/PrecipitationTrend.png)

    - use describe to calculate precipitation statistics

    ![](/Images/PrecipitationStatistics.png)

# Station Analysis
## Query and list stations

## Calculate number of stations using count function

    ![](/Images/StationCount..png)

## calculate distribution of observations by station
    - create variable for station count to inpute into session query
    - use func.count along with group by to perform calculation at station level

    ![](/Images/StationDistribution.png)

## create plot trending temperature by date
    - calculate date 12 months prior to most recent date
    - use session query to grab observations with time frame set by most recent date and start date
    - set date as index
    - plot trend using precipitation against date

    ![](/Images/TemperatureTrend.png)

# Create apps with routes, sharing query results vis a vi app.py
    - create homepage listing all related routes
        o /api/v1.0/precipitation
        o /api/v1.0/stations
        o /api/v1.0/tobs
        o /api/v1.0/<start>/<end>

    - create app querying on date and precipitation

    - create app querying on list of stations

    - create app querying on measurement class, showing obs for most active station over most recent 12  months
        o calculate most recent date and use strptime to allow query
        o calculate date 12 months prior to most recent date
        o use session query to grab observations with time frame set by most recent date and start date

    - create app supporting user based date range entered on webpage
        - create session variables allowing aliasing for func based variables
        - create date variables, using strptime to allow querying
        - allow jsonification using Numpy ravel function

