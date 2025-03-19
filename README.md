# WILDFIRE - Wildfire Impacts on Local Dynamics: Forests, Income, Residents, and Environment
Team members: Joyce Tongxin Cai, Yogerej Visvanathan, Kwame Donkor 

## Summary (JC: Introduction? We can do 'Abstract' additionally in the top if you like)
Wildfires are increasingly frequent and severe due to climate change and land-use patterns, posing significant threats to both the environment and human communities. 
In January 2025, the **Palisades and Eaton wildfires** in Los Angeles County caused widespread destruction, disproportionately affecting different socioeconomic groups. This study aimed to analyze the environmental & atmospheric conditions that contributed to its spread such as temperature, precipitation, wind speeds, vegetation density, and investigate the impact on various demographics. By integrating data on fire radiative power, climate reanalysis, land use & land cover, air quality and socioeconomic indicators, we seek to understand the relationship between atmospheric conditions, air quality, social vulnerability and wildfire damage, providing insights for future mitigation strategies. 
We sought to answer the questions: 
* What were the primary environmental factors driving the 2025 Palisades and Eaton wildfires in Los Angeles County, and how did these wildfires impact structure damage, vegetation, air quality, and socioeconomic communities?
* How can these insights prevent future widespread destruction by wildfires? 

## Datasets

* **Geospatial Boundaries (Vector):** Los Angeles County administrative boundary shapefiles. Source: [La Census Tract Shapefiles](https://redistricting.lacounty.gov/mapping-files-data-download/)
* **Fire Incident Data (Vector):** Wildfire burn perimeters, Fire progression data (FRP - Fire Radiative Power), Structure damage and destruction levels (DINS). Sources: [CAL FIRE](https://www.fire.ca.gov/), [NASA FIRMS](https://firms.modaps.eosdis.nasa.gov/)
* **Vegetation Data (Raster):** Vegetation index, moisture index, burned ratio index, 5-days temporal resolution and 10m spatial resolution especially for NDVI analysis. Sources: Sentinel-2 NDVI, NDMI, MSI, EVI, SAVI, GCI and NBRI ([Accessed using Microsoft's Planetary Computer platform](https://planetarycomputer.microsoft.com/dataset/sentinel-2-l2a#overview)).
* **Socioeconomic Data (Vector):** Social Vulnerability, Census tract-level demographics. Sources: [Social Vulnerability Index](https://www.atsdr.cdc.gov/place-health/php/svi/index.html)
* **Climate & Land Cover Data (Raster):** Temperature, Precipitation, Humidity, Wind speed & direction. Sources: [ERA5 Land Hourly Reanalysis Data](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-land?tab=overview), [ESA World Cover](https://worldcover2021.esa.int/) 
* **Air Quality Data:** Daily air pollutant concentrations including PM2.5, PM10, NO2, SO2, CO and O3; Computation of Air Quality Index (AQI) based on concentrations of air pollutants. Sources: [World Air Quality Index](https://aqicn.org/contact/) and [United States Environmental Protection Agency](https://www.epa.gov/aboutepa) 


### Python Packages Used 
- **Geospatial Data Handling & Analysis:** `geopandas`, `shapely`, `rioxarray`, `xarray`
- **Climate & Environmental Data Processing:** `pyproj`
- **Data Science & Statistical Analysis:** `numpy`, `pandas`, `scipy`, `metpy`
- **Visualization & Mapping:** `matplotlib`, `matplotlib.dates`, `cartopy`, `seaborn`, `Folium`, `plotly`, `plotly.express`, `plotly.graph_objects`, `contextily`, `windrose`
- **Remote Sensing & Fire Data:** `rasterio`, `odc.stac`, `pystac_client`, `planetary_computer`
- **Air Quality & Environmental Analysis:** `ozon3`

## Methodology (JC: A bit messy now, thinking subsetting for each dataset, and we can write our own part)

- Data Processing (Formatting & Cleaning):  Convert all datasets to a consistent Coordinate Reference System (e.g., EPSG 32611 - WGS 84 / UTM zone 11N)
- Geospatial Analysis:
  - Clipped vegetation and climate raster data to the Palisades and Eaton fire perimeter.
  - Clipped air pollutant concentrations data to the city of Los Angeles.
  - Intersected fire intensity/perimeters with census tracts to assess socioeconomic impact.
  - Analyzed fire intensity and structure damage relative to census tracts.
- Temporal Aggregation
  - Aggregate fire intensity (FRP) on a daily basis over wildfire duration.
  - Aggregate temperature, vegetation density indices, moisture indices and air pollutant concentrations data over wildfire duration for analysis. 
- Analysis
  - Correlated fire damage with socioeconomic factors (income, housing type, vulnerability).
  - Identified spatial clusters of fire damage and compare them with demographic data.
  - Identified vegetation loss using vegation density indices (NDVI, EVI, SAVI, GCI), moisture indices (NDMI and MSI) and burned ratio index (NBRI) analyses.
  - Identify air quality index based on air pollutant concentrations. 
- Environmental Contribution
  - Analyze relationships between vegetation density, NDVI anomalies, and fire perimeters.
  - Overlay wind direction and temperature data to identify conditions that influenced fire spread.
  - Assess pre- and post-fire changes in vegetation, air quality, and land use.

*** 

- Land Use Land Cover (LULC) Analysis
  - Overlay fire perimeter on LULC plot of Study Area and compute the areas of Built & Tree/Shrub/Grass Cover were affected by the fires.  
- Weather Variable Analysis
  - Investigate short & long-term (one-year) trends of weather variables in dataset (Temperature, Wind, Precipitation) and the calculated ones (Specific Humidity).
  - Calculate statistics on weather variables before and during the fire such as Wind Speeds & Direction. 
- Socioeconomic Analysis
  - Overlay fire perimeter on demographics plots such as Social Vulnerability Index, Aged Population, Young Population, etc. 
  - Calculate relevant statistics including populations affected per census tract. 

## Findings / Results 

...
{Insert relevant figures here}
- maps and figures demonstrating key findings
- analysis showing the relationship between wildfire impacts and socioeconomic variables

## Project File Structure 

* The various analyses were conducted in separate folders & notebooks and these can be identified from their names.
* For example, Land Use Land Cover and ERA5 (Weather) Analysis is done in *Land_Use_Land_Cover_ERA5_Land.ipynb* in the 'LULC_ERA5_Land' folder. 

## Future Directions  

#### Machine Learning and Interactive Maps
- Develop predictive models to identify potential future wildfire hotspots based on historical data and environmental factors.
- Create interactive maps and visualizations using libraries such as Folium and Plotly to present the findings in an accessible and informative manner.

## References 
- [1] Do, Vivian, et al. "Spatiotemporal distribution of power outages with climate events and social vulnerability in the USA." Nature communications 14.1 (2023): 2470. (https://www.nature.com/articles/s41467-023-38084-6)
- [2] https://www.climate.gov/news-features/event-tracker/weather-and-climate-influences-january-2025-fires-around-los-angeles#
- [3] https://www.nbclosangeles.com/weather-news/la-heat-wave-forecast/3502525/ 
- [4] https://www.usatoday.com/story/graphics/2025/01/11/santa-ana-winds-california-wildfires-explained/77592518007/
- [5] https://www.weather.gov/pqr/wind
