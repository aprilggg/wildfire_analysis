# Wildfire Analysis for Lawton, OK
Summers in the western United States are increasingly marked by wildfires, with smoke stretching across multiple states. Proposed causes include climate change, U.S. Forestry policy, and heightened awareness, among others. Regardless of the origin, the impact of wildland fires is extensive, with a growing body of research highlighting their negative effects on health, tourism, property, and various societal aspects.

This project entails an analysis of wildfire impacts on a specific U.S. city: Lawton, OK. The ultimate objective is to provide insights that can inform policy makers, city managers, city councils, and other civic institutions in developing informed plans. These plans should address whether and how to mitigate future impacts stemming from wildfires.

## Part 1: Common Analysis
### Objective
Conduct a base analysis to assess the implications of wildfires in Lawton, OK. 
### Data Source
* [Wildfire Dataset](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) from US Geological Survey:

The "USGS_Wildland_Fire_Combined_Dataset.json" was sourced from the USGS website. The JSON dictionary within this dataset encompasses keys such as 'displayFieldName', 'fieldAliases', 'geometryType', 'spatialReference', 'fields', and 'features'. The 'features' section further breaks down into 'attributes' and 'geometry', where 'attributes' provide information on fire year, fire type, acres burnt, and more, while 'geometry' entails coordinates for the wildfire locations. Following data cleaning, an output data file was generated, encompassing details on wildfires occurring within a 1250-mile radius of Lawton over the past 50 years. This file includes information on the year, acres burnt, and distance from the city.

* [AQI data](https://aqs.epa.gov/data/api):
  
The Air Quality Index (AQI) data was obtained from the US Environmental Protection Agency using an API key. The request comprised various GASEOUS and PARTICULATES components, each associated with its AQI for Lawton City. The resulting output data file presents the average yearly AQI spanning from 1988 to 2023.

### Consideration
It's important to note that the wildfire dataset incorporates both wildfire and prescribed fire types. This analysis considers both because all types of fires can impact air quality. Additionally, the AQI monitoring station in Lawton City lacks AQI values for certain specific pollutants. To address this, the analysis utilizes the average AQI for all pollutants in the calculations.

### Reference Notebook
* [Example code](https://drive.google.com/file/d/1qNI6hji8CvDeBsnLDAhJXvaqf2gcg8UV/view?usp=sharing) to process wildfire data
* [Example code](https://drive.google.com/file/d/1bxl9qrb_52RocKNGfbZ5znHVqFDMkUzf/view?usp=sharing) to request AQI data
