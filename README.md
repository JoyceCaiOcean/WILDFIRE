# WILDFIRE - Wildfire Impacts on Local Dynamics: Forests, Income, Residents, and Environment
Team members: Joyce Tongxin Cai, Yogerej Visvanathan, Kwame Donkor 

## Abstract

{Version one}

Wildfires have become increasingly frequent and severe due to climate change and land-use patterns, significantly impacting ecosystems and human communities. This study focuses on the **January 2025 Palisades and Eaton wildfires** in Los Angeles County, integrating multi-source data to analyze fire behavior, environmental drivers, and socioeconomic impacts.  

By leveraging **fire radiative power (FRP) data** from multiple satellite sources, we quantified the fire's intensity and progression over time. Our findings indicate that the **wildfire spread was driven primarily by strong northeast winds**, compounded by **dry vegetation and prior wet winters** that fueled fire growth. The analysis of air quality data revealed a **sharp increase in PM2.5 concentrations**, leading to **hazardous air quality conditions** throughout the affected areas.  

The **structural impact assessment** showed that **64% of homes in Palisades and 51% in Eaton were destroyed**, with damage disproportionately affecting **high-income and elderly populations** in certain census tracts. Vegetation analysis using **Normalized Burn Ratio Index (NBRI)** confirmed that **nearly 100% of the burned regions had no regrowth potential**, emphasizing the long-term environmental consequences.  

Our research underscores the interconnected nature of **wildfire intensity, atmospheric conditions, air pollution, and social vulnerability**, providing critical insights for future **wildfire risk assessment and mitigation strategies**. The study suggests that **enhanced forecasting models** and **targeted community resilience planning** could help reduce wildfire-related destruction in the future.  


{Version two}

Wildfires are becoming increasingly severe due to climate change and land-use patterns, posing serious risks to both ecosystems and communities. This study examines the **January 2025 Palisades and Eaton wildfires** in Los Angeles County, analyzing fire behavior, environmental drivers, and socioeconomic impacts using multi-source data.  

### **Key Findings:**  

- **Fire Behavior & Environmental Drivers:**  
  - The wildfire spread was **driven primarily by strong northeast winds**.  
  - **Dry vegetation**, fueled by **past wet winters**, contributed to rapid fire growth.  

- **Fire Intensity & Structure Damage:**  
  - Fire Radiative Power (FRP) analysis showed significant fire intensity over time.  
  - **64% of homes in Palisades** and **51% in Eaton** were **destroyed**.  
  - Structural damage was **disproportionately higher** in census tracts with **high-income and elderly populations**.  

- **Air Quality Impact:**  
  - The wildfire caused a **sharp increase in PM2.5 concentrations**, leading to **hazardous air quality conditions**.  

- **Vegetation Loss & Recovery Potential:**  
  - **Nearly 100% of burned regions had no regrowth potential**, based on **Normalized Burn Ratio Index (NBRI)** analysis.  

- **Broader Implications:**  
  - Wildfire intensity, **atmospheric conditions, air pollution, and social vulnerability** are closely linked.  
  - Findings highlight the need for **improved wildfire forecasting models** and **targeted community resilience planning** to mitigate future risks.  

By integrating geospatial, environmental, and socioeconomic data, this study provides insights to support **wildfire risk assessment and future mitigation strategies**.  

## Introduction

Wildfires are becoming more frequent and intense due to climate change and land-use patterns, posing serious risks to both ecosystems and human communities.  
In January 2025, the **Palisades and Eaton wildfires** in Los Angeles County caused widespread destruction, disproportionately affecting different socioeconomic groups.  

This study analyzes the environmental and atmospheric conditions that influenced wildfire spread—including temperature, precipitation, wind speeds, and vegetation density—and examines their impact on air quality and vulnerable communities. By integrating data on fire radiative power, climate reanalysis, land use and land cover, air quality, and socioeconomic indicators, we aim to uncover the relationships between atmospheric conditions, social vulnerability, and wildfire damage. These insights can inform future mitigation strategies to reduce wildfire risks.  

### Research Questions  
- What were the primary environmental factors driving the 2025 Palisades and Eaton wildfires?
- How did these wildfires impact structure damage, vegetation, air quality, and socioeconomic communities? 

![Study Area](images/study_area.png)
*Figure 1: 2025 January Wildfire in Los Angeles County. Source: [Penitentes in Wikipedia](https://en.m.wikipedia.org/wiki/File:January_2025_Southern_California_wildfires_map.png).*


## Datasets

* **Geospatial Boundaries (Vector):** Los Angeles County administrative boundary shapefiles. Source: [La Census Tract Shapefiles](https://redistricting.lacounty.gov/mapping-files-data-download/)
* **Fire Incident Data (Vector):** Wildfire burn perimeters, Fire progression data (FRP - Fire Radiative Power), Structure damage and destruction levels (DINS). Sources: [CAL FIRE](https://www.fire.ca.gov/), [NASA FIRMS](https://firms.modaps.eosdis.nasa.gov/)
* **Vegetation Data (Raster):** Vegetation index, moisture index, burned ratio index with 5-days temporal resolution and 10m-20m spatial resolution. Sources: Sentinel-2 NDVI, NDMI, MSI, EVI, SAVI, GCI and NBRI ([Accessed using Microsoft's Planetary Computer platform](https://planetarycomputer.microsoft.com/dataset/sentinel-2-l2a#overview)).
* **Socioeconomic Data (Vector):** Social Vulnerability, Census tract-level demographics. Sources: [Social Vulnerability Index](https://www.atsdr.cdc.gov/place-health/php/svi/index.html)
* **Climate & Land Cover Data (Raster):** Temperature, Precipitation, Humidity, Wind speed & direction. Sources: [ERA5 Land Hourly Reanalysis Data](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-land?tab=overview), [ESA World Cover](https://worldcover2021.esa.int/) 
* **Air Quality Data (Tabular):** Daily air pollutant concentrations including PM2.5, PM10, NO2, SO2, CO and O3; Computation of Air Quality Index (AQI) based on concentrations of air pollutants. Sources: [World Air Quality Index](https://aqicn.org/contact/) and [United States Environmental Protection Agency](https://www.epa.gov/aboutepa) 


### Python Packages Used 
- **Geospatial Data Handling & Analysis:** `geopandas`, `shapely`, `rioxarray`, `xarray`
- **Climate & Environmental Data Processing:** `pyproj`
- **Data Science & Statistical Analysis:** `numpy`, `pandas`, `scipy`, `metpy`
- **Visualization & Mapping:** `matplotlib`, `matplotlib.dates`, `cartopy`, `seaborn`, `Folium`, `plotly`, `plotly.express`, `plotly.graph_objects`, `kaleido`, `contextily`, `windrose`
- **Remote Sensing & Fire Data:** `rasterio`, `odc.stac`, `pystac_client`, `planetary_computer`
- **Air Quality & Environmental Analysis:** `ozon3`

## Methodology
- Data Processing (Formatting & Cleaning):  Convert all datasets to a consistent Coordinate Reference System (e.g., EPSG 32611 - WGS 84 / UTM zone 11N)
- Fire Intensity Analysis
  - Integrated fire radiative power (FRP) data from five satellite sources and resampled them to a daily scale for each region.  
  - Computed fire intensity based on pixel size to analyze fire spread and derived the time series of total daily radiative power.  
  - Generated a correlation heatmap to assess relationships between fire radiative power, temperature, wind speed, precipitation, and humidity, identifying key driving factors.  
  - Analyzed the correlation between fire radiative power and air pollutant concentrations (PM2.5 and PM10) to evaluate the fire’s impact on air quality.  
- Fire Structure Analysis
  - Assessed the distribution of structural damage across different damage levels.  
  - Examined damage patterns within census tracts to identify spatial variations in fire impact.  
- Land Use Land Cover (LULC) Analysis
  - Overlay fire perimeter on LULC plot of Study Area and compute the areas of Built & Tree/Shrub/Grass Cover were affected by the fires.
- Vegetation Density Analysis
  - Investigated vegetation density using vegetation, moisture and burned ratio indices.
  - Created mask to remove cloud cover pixels using SCL from Sentinel-2
  - Calculated delta NBRI from the difference between pre-fire NBRI and post-fire NBRI to determine vegetation regrowth potential in the area of study.
- Air Quality Analysis
  - Investigated air pollutant concentrations during wildfire and throughout January 2025 from the World Air Quality Index database and US EPA.
  - Calculated Air Quality Index (AQI) based on the concentration of air pollutants. 
- Weather Variable Analysis
  - Investigate short & long-term (one-year) trends of weather variables in dataset (Temperature, Wind, Precipitation) and the calculated ones (Specific Humidity).
  - Calculate statistics on weather variables before and during the fire such as Wind Speeds & Direction. 
- Socioeconomic Analysis
  - Overlay fire perimeter on demographics plots such as Social Vulnerability Index, Aged Population, Young Population, etc. 
  - Calculate relevant statistics including populations affected per census tract. 

## Findings / Results 
![Palisades_Fire_Time_Series](images/palisades_fire.png)
*Figure 2: Palisades fire spread, colored by fire radiative power density.*

![Eaton_Fire_Time_Series](images/eaton_fire.png)
*Figure 3: Eaton fire spread, colored by fire radiative power density.*


* The wildfire was driven by **strong NE winds** and fueled by the **past wet winters & dry** conditions.


* The **impacts** of the fire on:

    * **Structure damage:** 64% (Palisades) & 51% (Eaton) of houses destroyed.
        ![Fire_Structure_Damage](images/Fire_Structure.png)
        *Figure X: Wildfire impact on structure damage in Palisades and Eaton.*

    * **Vegetation:** ~ 100% of Palisades and Eaton have no regrowth potential.
    * **Air quality:** Very unhealthy AQI (high PM2.5 concentrations). 
    * **Socio-economics:** Majority of high-income & aged people affected. 


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
