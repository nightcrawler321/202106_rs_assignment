# 202106_rs_assignment
Technical assignment for the geospatial data scientist position.


# Background
In this assignment, we're trying to better understand the NO2 emissions from Paris, following a simplified version of [Lorente et al. 2019](http://www.nature.com/articles/s41598-019-56428-5)


# Assignment

## Expectations
We expect you to fill the following tasks / answer the following questions in either a Jupyter notebook or a Markdown document with attached Python code. You are expected to use one or several of the following packages: `numpy`, `scipy`, `OpenCV`, `xarray`. The use of `shapely` or `geopandas` should be avoided.

## Downloading data
In this assignment, you should rely on the data available here.

The dataset contains:
- daily NO2 troposheric column density retrieved from [Sentinel5P OFFL/L3_NO2](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S5P_OFFL_L3_NO2) dataset.
- daily wind speed (`u` and `v`) components from [ERA5](https://developers.google.com/earth-engine/datasets/catalog/ECMWF_ERA5_DAILY)

## Task #1: Building NO2 density lines
For every single day, we are willing to build a **NO2 density line** along wind direction between -30km and 30km, centered on Paris center (48.8566° N, 2.3522° E).
Please generate one csv per day with distance and density information.


## Task #2:






