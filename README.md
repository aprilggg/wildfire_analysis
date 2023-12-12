# Wildfire Analysis for Lawton, OK
In recent years, the growing frequency and intensity of wildfires have posed unprecedented challenges to communities worldwide, and Lawton City is no exception. The threat of wildfires extends beyond the immediate danger to human life and property, permeating into various facets of community well-being, environmental stability, and economic sustainability. 

At its core, this analysis seeks to address a real and immediate problem faced by Lawton City—how wildfires impact the employment landscape within the tourism sector. The resilience of the city's workforce and the sustainability of local businesses are at stake, making it important  to understand the nuances of this complex interplay. By tackling this unresolved research question, we aspire to contribute not only to Lawton City's recovery efforts but also to the broader discourse on mitigating the economic fallout of wildfires in tourism-dependent regions.
## Goal
The Goal for this analysis is following:

* Examine the historical wildfire impact over the past 50 years (1963-2023) and forecast the potential future wildfire impact.

* Evaluate the hypothesis that a rise in wildfires is associated with a decrease in tourism employment in Lawton.

## Data Source 
### Raw Data: 
Stored in `data_raw` folder

* [Wildfire Dataset](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) from US Geological Survey:

The "USGS_Wildland_Fire_Combined_Dataset.json" was sourced from the USGS website. The JSON dictionary within this dataset encompasses keys such as 'displayFieldName', 'fieldAliases', 'geometryType', 'spatialReference', 'fields', and 'features'. The 'features' section further breaks down into 'attributes' and 'geometry', where 'attributes' provide information on fire year, fire type, acres burnt, and more, while 'geometry' entails coordinates for the wildfire locations. Following data cleaning, an output data file was generated, encompassing details on wildfires occurring within a 1250-mile radius of Lawton over the past 50 years. This file includes information on the year, acres burnt, and distance from the city.

* [AQI data](https://aqs.epa.gov/data/api):
  
The Air Quality Index (AQI) data was obtained from the US Environmental Protection Agency using an API key. The request comprised various GASEOUS and PARTICULATES components, each associated with its AQI for Lawton City. The resulting output data file presents the average yearly AQI spanning from 1988 to 2023.

* [Tourism Employment Data in Lawton](https://www.bls.gov/eag/eag.ok_lawton_msa.htm)
This dataset is sourced from the U. S. Bureau of Labor Statistics. It contains monthly numbers of jobs(in thousands) in Leisure and Hospitalit from 1990 to 2023 in Lawton.

### Intermediate Data
Stored in `data_intermediate` folder

* `wild_fire_data.csv` contains the total acres burnt, year, and distance from Lawton for each wildfire
  
* `smoke est.csv` contains the smoke estimate for each year for the past 50 years that is within 1250 miles from Lawton
  
* `smoke prediction.csv` contains the predicted yearly smoke estimate for the next 25 years
  
* `yearly_aqi.csv` contains the yearly average AQI for all the pollutants in Lawton

## Consideration
The AQI monitoring station in Lawton City lacks specific values for certain pollutants, prompting the use of average AQI calculations in this analysis to address the gaps. This approach allows for a comprehensive evaluation, although it acknowledges the absence of pollutant-specific data.

In gauging the impact of wildfires, the smoke estimate encompasses various fire types, including prescribed fires, and is derived from the average of all wildfires within a 1250-mile radius from Lawton. However, this expansive range may dilute the relevance of the smoke estimate to Lawton, introducing a limitation to the precision of the analysis.

During the examination of employment data, a notable drop in employment was observed in 2020. To maintain the integrity of the analysis, the employment data for 2020 was excluded due to the potential distortions caused by the pandemic.

## Notebook
The notebooks used for this analysis is stored in `code` folder

### `Part 1-Common Analysis.ipynb`
This notebook outlines the procedures for cleaning wildfire data, generating smoke estimates for each year, and forecasting future smoke estimates. Partial code was referenced to the example code listed in Reference notebook.

### `Part 1-AQI History.ipynb`
This notebook provides a comprehensive overview of the data acquisition and cleaning processes for Air Quality Index (AQI) data. Partial code was referenced to the example code listed in Reference notebook.

### `Part 2 -Employment Analysis.ipynb`
This notebook encompasses the procedures for comprehending the influence of wildfires on tourism employment. It further incorporates predictive modeling to anticipate future trends in tourism employment using the future smoke estimates.

### Reference notebook
Provided by Dr. David McDonald under the [CC-BY license](https://creativecommons.org/licenses/by/4.0/):
* [Example code](https://drive.google.com/file/d/1qNI6hji8CvDeBsnLDAhJXvaqf2gcg8UV/view?usp=sharing) to process wildfire data
* [Example code](https://drive.google.com/file/d/1bxl9qrb_52RocKNGfbZ5znHVqFDMkUzf/view?usp=sharing) to request AQI data
