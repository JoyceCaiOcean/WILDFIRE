# WILDFIRE - Wildfire Impacts on Local Dynamics: Forests, Income, Residents, and Environment
Team member: Joyce Tongxin Cai, Yogerej Visvanathan, Kwame Donkor

## Research Question
How did the 2025 Palisades and Eaton wildfires in Los Angeles County impact various socioeconomic communities, and what were the primary factors contributing to the extent of the damage?

## Introduction
Wildfires are increasingly frequent and severe due to climate change and land-use patterns, posing significant threats to both the environment and human communities. In 2025, the **Palisades and Eaton wildfires** in Los Angeles County caused widespread destruction, disproportionately affecting different socioeconomic groups. This study aims to analyze the impact of these wildfires on various communities, examining key factors such as vegetation density, wind patterns, and economic vulnerability. By integrating geospatial data and socioeconomic indicators, we seek to understand the relationship between wildfire damage and community resilience, providing insights for future mitigation strategies.


## Dataset

### 1. Data Collection

#### Fire Incident Data (Vector)
- **Sources:** [CAL FIRE](https://www.fire.ca.gov/), [NASA FIRMS](https://firms.modaps.eosdis.nasa.gov/)
- **Key Data:**
  - Wildfire burn perimeters
  - Fire progression data (FRP - Fire Radiative Power)
  - Structure damage and destruction levels (DINS)

#### Vegetation and Landcover Data (Raster)
- **Sources:** Sentinel-2 NDVI, NDMI, MSI, EVI, SAVI, GCI and NBRI ([Accessed using Microsoft's Planetary Computer platform](https://planetarycomputer.microsoft.com/dataset/sentinel-2-l2a#overview))
- **Key Data:**
  - Vegetation index, moisture index, burned ratio index
  - 5-days temporal resolution and 10m spatial resolution especially for NDVI analysis

#### Socioeconomic Data (Vector)
- **Sources:** [U.S. Census Bureau](https://www.census.gov/), [FEMA Social Vulnerability Index](https://hazards.fema.gov/nri/map)
- **Key Data:**
  - Census tract-level demographics
  - Social vulnerability, income, housing type, population density

#### Climate Data (Raster)
- **Sources:** ERA5 Reanalysis Data
- **Key Data:**
  - Temperature, wind speed, and wind patterns during fire events

#### Geospatial Boundaries (Vector)
- **Sources:** [USGS](https://www.usgs.gov/)
- **Key Data:**
  - Los Angeles County administrative boundary shapefiles

#### Air Quality Data
- **Sources:** [World Air Quality Index](https://aqicn.org/contact/) and [United States Environmental Protection Agency](https://www.epa.gov/aboutepa)
- **Key Data:**
  - Daily air pollutant concentrations including PM2.5, PM10, NO2, SO2, CO and O3
  - Computation of Air Quality Index (AQI) based on concentrations of air pollutants

### 2. Python Packages to use
- **Geospatial Data Handling & Analysis:** `geopandas`, `shapely`, `rioxarray`, `xarray`
- **Climate & Environmental Data Processing:** `pyproj`
- **Data Science & Statistical Analysis:** `numpy`, `pandas`, `scipy`, `metpy`
- **Visualization & Mapping:** `matplotlib`, `matplotlib.dates`, `cartopy`, `seaborn`, `Folium`, `plotly`, `plotly.express`, `plotly.graph_objects`, `contextily`, `windrose`
- **Remote Sensing & Fire Data:** `rasterio`, `odc.stac`, `pystac_client`, `planetary_computer`
- **Air Quality & Environmental Analysis:** `ozon3`

### 3. Data Processing

#### Format and Cleaning
- Convert all datasets to a consistent Coordinate Reference System (e.g., EPSG 32611 - WGS 84 / UTM zone 11N)

#### Spatial Analysis
- Clip vegetation and climate raster data to the Palisades and Eaton fire perimeter.
- Clip air pollutant concentrations data to the city of Los Angeles.
- Intersect fire intensity/perimeters with census tracts to assess socioeconomic impact.
- Analyze fire intensity and structure damage relative to census tracts.

#### Temporal Aggregation
- Aggregate fire intensity (FRP) on a daily basis over wildfire duration.
- Aggregate temperature, vegetation density indices, moisture indices and air pollutant concentrations data over wildfire duration for analysis.

## Analysis

### 1. Methodology

#### Impact Assessment
- Correlate fire damage with socioeconomic factors (income, housing type, vulnerability).
- Identify spatial clusters of fire damage and compare them with demographic data.
- Identify vegetation loss using NDVI, NDMI, MSI, EVI, SAVI, GCI and NBRI analyses.
- Identify air quality index based on air pollutant concentrations.

#### Environmental Contribution
- Analyze relationships between vegetation density, NDVI anomalies, and fire perimeters.
- Overlay wind direction and temperature data to identify conditions that influenced fire spread.
- Assess pre- and post-fire changes in vegetation, air quality, and land use.

### 2. Visualization

#### Maps
- Thematic maps displaying fire perimeters, vegetation density (NDVI, EVI, SAVI, GCI ), mositure index (NDMI, and MSI) , burned ratio index (NBRI) and socioeconomic data.

#### Charts
- **Time-series line plots:** Fire intensity, vegetation density indices, moisture indices and temperature variations over wildfire duration.
- **Scatter plots:** Correlations between fire damage, socioeconomic factors, and environmental conditions.

## Expected Deliverables
- A clear analysis showing the relationship between wildfire impacts and socioeconomic variables.
- High-quality maps and figures demonstrating key findings.
- Insights into evacuation strategies for future extreme events.

## Reference
- [1] Do, Vivian, et al. "Spatiotemporal distribution of power outages with climate events and social vulnerability in the USA." Nature communications 14.1 (2023): 2470. (https://www.nature.com/articles/s41467-023-38084-6)
- [2] https://www.nbclosangeles.com/weather-news/la-heat-wave-forecast/3502525/ 
- [3] https://www.usatoday.com/story/graphics/2025/01/11/santa-ana-winds-california-wildfires-explained/77592518007/
- [4] https://www.climate.gov/news-features/event-tracker/weather-and-climate-influences-january-2025-fires-around-los-angeles#
- [5] https://abc7.com/post/la-fires-aftermath-look-recovery-process-2-months-eaton-palisades/15988311/
- [6] https://www.weather.gov/pqr/wind
