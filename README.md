# WILDFIRE - Wildfire Impacts on Local Dynamics: Forests, Income, Residents, and Environment
Team member: Joyce Tongxin Cai, Yogerej Visvanathan, Kwame Donkor

## Research Question
How did the 2025 Palisades and Eaton wildfires in Los Angeles County impact various socioeconomic communities, and what were the primary factors contributing to the extent of the damage?

## Introduction
Wildfires are increasingly frequent and severe due to climate change and land-use patterns, posing significant threats to both the environment and human communities. In 2025, the **Palisades and Eaton wildfires** in Los Angeles County caused widespread destruction, disproportionately affecting different socioeconomic groups. This study aims to analyze the impact of these wildfires on various communities, examining key factors such as vegetation density, wind patterns, and economic vulnerability. By integrating geospatial data and socioeconomic indicators, we seek to understand the relationship between wildfire damage and community resilience, providing insights for future mitigation strategies.


## Dataset

### 1. Data Collection
- **Fire Incident Data (Vector):** Obtain wildfire burn perimeters, ignition points, and fire progression data from [CAL FIRE](https://www.fire.ca.gov/) or [NASA FIRMS](https://firms.modaps.eosdis.nasa.gov/).
- **Vegetation and Landcover Data (Raster):** Use [MODIS NDVI](https://modis.gsfc.nasa.gov/data/dataprod/mod13.php) (Vegetation Indices 16-Day L3 Global 250m) or Sentinel-2 NDVI data to assess vegetation density and type. Another dataset is the daily 0.05-degree [NDVI](https://www.ncei.noaa.gov/products/climate-data-records/normalized-difference-vegetation-index) derived from the Surface Reflectance Climate Data Record (CDR).
- **Socioeconomic Data (Vector):** Retrieve census tract-level demographic and socioeconomic data (e.g., [social vulnerability](https://hazards.fema.gov/nri/map), income, housing type, population density) from the U.S. Census Bureau.
- **Climate Data (Raster):** ERA5 reanalysis data for temperature and wind patterns during the fire events.
- **Geospatial Boundaries (Vector):** Access Los Angeles County administrative boundary shapefiles from [USGS](https://www.usgs.gov/).
- **Air Quality:** USEPA Environmental Quality Index (EQI).

### 2. Python Packages to use
- **Geospatial Data Handling & Analysis:** `geopandas`, `shapely`, `rioxarray`
- **Climate & Environmental Data Processing:** `pyproj`
- **Data Science & Statistical Analysis:** `numpy`, `pandas`, `scipy`
- **Visualization & Mapping:** `matplotlib`, `cartopy`, `Folium`, `plotly`
- **Remote Sensing & Fire Data:**
- **Air Quality & Environmental Analysis:**

### 3. Data Processing
- **Format and Clean Data:** Convert all datasets to the same Coordinate Reference System (e.g., WGS 84).
- **Spatial Analysis:**
  - Clip vegetation and climate raster data to the LA County boundary.
  - Intersect fire perimeters with census tracts to analyze impacts on socioeconomic variables.
- **Temporal Aggregation:** Aggregate temperature and NDVI data over the wildfire duration for meaningful analysis.

## Analysis
### 1. Methodology
- **Impact Assessment:**
  - Correlate fire damage with socioeconomic variables (e.g., income, housing type).
  - Identify spatial clusters of fire damage.
- **Environmental Contribution:**
  - Analyze relationships between vegetation density, NDVI anomalies, and fire perimeters.
  - Overlay wind direction and temperature data to identify conditions that influenced fire spread.
  - Analyze changes in vegetation, air quality, and land use before and after the wildfire.

### 2. Visualization
- **Maps:** Thematic maps showing fire perimeters, vegetation density (NDVI), and socioeconomic data.
- **Charts:**
  - Line plots showing time-series changes in NDVI and temperature during the fires.
  - Scatter plots correlating fire damage with socioeconomic and environmental factors.

## Machine Learning and Interactive Maps (if time permits)
- Develop predictive models to identify potential future wildfire hotspots based on historical data and environmental factors.
- Create interactive maps and visualizations using libraries such as Folium and Plotly to present the findings in an accessible and informative manner.

## Expected Deliverables
- A clear analysis showing the relationship between wildfire impacts and socioeconomic variables.
- High-quality maps and figures demonstrating key findings.
- Insights into evacuation strategies for future extreme events.

## Reference
[1] Do, Vivian, et al. "Spatiotemporal distribution of power outages with climate events and social vulnerability in the USA." Nature communications 14.1 (2023): 2470. (https://www.nature.com/articles/s41467-023-38084-6)
