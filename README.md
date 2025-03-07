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
- **Sources:** [MODIS NDVI](https://modis.gsfc.nasa.gov/data/dataprod/mod13.php), Sentinel-2 NDVI, [NDVI Climate Data Record (CDR)](https://www.ncei.noaa.gov/products/climate-data-records/normalized-difference-vegetation-index)
- **Key Data:**
  - Vegetation density and classification
  - Daily 0.05-degree NDVI for temporal analysis

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
- **Sources:** USEPA Environmental Quality Index (EQI)
- **Key Data:**
  - Pre- and post-fire air quality measures

### 2. Python Packages to use
- **Geospatial Data Handling & Analysis:** `geopandas`, `shapely`, `rioxarray`
- **Climate & Environmental Data Processing:** `pyproj`
- **Data Science & Statistical Analysis:** `numpy`, `pandas`, `scipy`
- **Visualization & Mapping:** `matplotlib`, `cartopy`, `Folium`, `plotly`, `contextily`
- **Remote Sensing & Fire Data:** `rasterio`, `SentinelHub`, `PyTorch`
- **Air Quality & Environmental Analysis:** `pandas`, `numpy`, `SciPy`, `Matplotlib`, `Seaborn`

### 3. Data Processing

#### Format and Cleaning
- Convert all datasets to a consistent Coordinate Reference System (e.g., EPSG: 3310 - California Albers)

#### Spatial Analysis
- Clip vegetation and climate raster data to the Palisades and Eaton fire perimeter.
- Intersect fire intensity/perimeters with census tracts to assess socioeconomic impact.
- Analyze fire intensity and structure damage relative to census tracts.

#### Temporal Aggregation
- Aggregate fire intensity (FRP) on a daily basis over wildfire duration.
- Aggregate temperature and NDVI data over wildfire duration for analysis.

## Analysis

### 1. Methodology

#### Impact Assessment
- Correlate fire damage with socioeconomic factors (income, housing type, vulnerability).
- Identify spatial clusters of fire damage and compare them with demographic data.

#### Environmental Contribution
- Analyze relationships between vegetation density, NDVI anomalies, and fire perimeters.
- Overlay wind direction and temperature data to identify conditions that influenced fire spread.
- Assess pre- and post-fire changes in vegetation, air quality, and land use.

### 2. Visualization

#### Maps
- Thematic maps displaying fire perimeters, vegetation density (NDVI), and socioeconomic data.

#### Charts
- **Time-series line plots:** Fire intensity, NDVI, and temperature variations over wildfire duration.
- **Scatter plots:** Correlations between fire damage, socioeconomic factors, and environmental conditions.

## Machine Learning and Interactive Maps (if time permits)
- Develop predictive models to identify potential future wildfire hotspots based on historical data and environmental factors.
- Create interactive maps and visualizations using libraries such as Folium and Plotly to present the findings in an accessible and informative manner.

## Expected Deliverables
- A clear analysis showing the relationship between wildfire impacts and socioeconomic variables.
- High-quality maps and figures demonstrating key findings.
- Insights into evacuation strategies for future extreme events.

## Reference
[1] Do, Vivian, et al. "Spatiotemporal distribution of power outages with climate events and social vulnerability in the USA." Nature communications 14.1 (2023): 2470. (https://www.nature.com/articles/s41467-023-38084-6)
