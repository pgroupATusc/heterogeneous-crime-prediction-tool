Main Backend Code/ML Stuff
---
This directory contains files for the back-end clustering and prediction algorithms, their associated helper functions, and file I/O.
> djmaps/src/prediction/fwdfiles

___

General Functions
--
> djmaps/src/prediction/fwdfiles/general_functions.py

**Map-related Functions**
- **getBorderCoordinates** - given a cell number i and j, returns the coordinates of the cell's borders
- **getAreaFromLatLon** - calculates the area between 2 sets of coordinates, not sure what the definiton of "area" is (I assume it's two corners of a cell)
- **haversine** - calculates the great-circle distance between two sets of coordinates

**I/O-related Functions**
- **savePredictions** - saves crime predictions (clusters, forecasts, etc.) to disk
- **saveParameters** - saves configuration (clustering configuration, prediction configuration) for a given prediction
- **getIfParametersExists** - reads parameters (configuration) file from disk

**Misc. Functions**
- **plotTimeSeries** - plots predictions as a time series using matplotlib
- **computeResourceAllocation** - ?? // todo

Cluster Functions
--
> djmaps/src/prediction/fwdfiles/cluster_functions.py

This file contains functions related to computing clusters and organizing data for a given input. We likely will not need to modify this file, though the function **computeClustersAndOrganizeData** is called upon in the *views.py* file:
> djmaps/src/crimePred/views.py

Forecast [Model]
--
The following files actually make the crime predictions (forecasts) and save their results. These main functions are called upon in *views.py*: **forecast_MM, forecast_ARIMA, forecast_LSTM**

**Moving Mean (MM)** 
> djmaps/src/prediction/fwdfiles/forecast_MM.py

**Autoregressive Integrated Moving Average (ARIMA)**
> djmaps/src/prediction/fwdfiles/forecast_ARIMA.py

**Long Short-Term Memory (LSTM)**
> djmaps/src/prediction/fwdfiles/forecast_LSTM.py

Resource Allocation Functions
--
> djmaps/src/prediction/fwdfiles/resourceAllocation_functions.py

This file relates to resource allocation (i.e. how many officers to place where) on a given date, and computes the effectiveness of the forecasts. It does not yet seem to be implemented anywhere in the front-end, though it is used in the following file:
> djmaps/src/prediction/calculate_resource_allocation.py