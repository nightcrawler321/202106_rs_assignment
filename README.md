# Technical Assignment

Technical assignment for the geospatial data scientist position at [CREA](https://energyandcleanair.org) (June 2021).

# Background

In this assignment, we are trying to better understand NO2 emissions from Paris, using Sentinel-5P TROPOMI sensor, following a simplified version of [Lorente et al. 2019](http://www.nature.com/articles/s41598-019-56428-5) and [de Foy et al. 2014](http://acmg.seas.harvard.edu/publications/aqast/articles/defoy_et_al_2014_ae.pdf).

We expect you to fill the following tasks / answer the following questions using Python.

To submit your results, please share a repository to `hubert-thieriot` on GitHub, that contains either a Jupyter notebook or a Markdown document with attached Python code and results.

If you have any question or comment, please reach out to [hubert@energyandcleanair.org](mailto:hubert@energyandcleanair.org)

Have fun!

## Dataset

For this assignment, you only need to rely on the attached [geotiffs](data/):

- daily NO2 troposheric column density retrieved from [Sentinel5P OFFL/L3_NO2](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S5P_OFFL_L3_NO2) dataset; and
- daily wind speed (`u` and `v`) components from [ERA5](https://developers.google.com/earth-engine/datasets/catalog/ECMWF_ERA5_DAILY).


## Task #1: Building NO2 density lines
For every single day of the dataset, we are willing to build a **NO2 density line** along wind direction between -30km (upwind) and 30km (downwind), centered on Paris center (48.8566° N, 2.3522° E). For each point along this line, the NO2 density is defined as the integration (sum) of NO2 column density perpendicular to the wind direction over a 60km interval (similar to [Lorente et al. 2019](http://www.nature.com/articles/s41598-019-56428-5)).

Please generate one csv per day with distance and density information, as well as accompanying line plots. NA values in the remote sensing data should simply be ignored.

## Task #2: Estimating emissions
To extract some information from the NO2 density line, we will use the exponentially-modified gaussian approach defined in ([de Foy et al. 2014, section 2.5](http://acmg.seas.harvard.edu/publications/aqast/articles/defoy_et_al_2014_ae.pdf)).

This method suggests to fit the NO2 density line with the following function:

![equation](equation.png)

with:

- L<sub>fit</sub>: the fitted version of the line density identified in previous task
- E: NOx emission
- U: wind speed
- x - µ<sub>x</sub>: position along the line density axis (x-µ<sub>x</sub>)=0 in Paris
- x<sub>0</sub>: length scale for chemical decay

For each day of the dataset, determine the optimal parameters a, x<sub>0</sub> and σ<sub>x</sub>. Based on the result parameters, what can you say about the emissions in the selected days?