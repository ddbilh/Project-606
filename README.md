# Project-606
Introduction:

The District of Columbia's housing market is notorious for being one of the most expensive and competitive cities in the country to buy . An article from NPR says one of the main reasons is due to the price of land in the District (Schweitzer). Understanding the different factors that make a house more marketable can have a personal impact when looking to sell or buy in the area for potential fair asking price, but it also can have public interest in understanding how neighborhoods and quality of houses can be invested in without pricing the existing people out. 

Literary Review: 

The article, "Machine Learning Project: Predicting Boston Housing Prices with Regression" by Victor Roman, is about predicting Boston Housing Prices with the Decision Tree Regressor model. This study used 3 features (poverty of neighborhood, number of rooms, and pupil to student ratio of nearest school) to run a model to predict housing prices. They used a GridSearchCV to find the correct parameters for the model. A big takeaway from the author was the limited feature to predict the prices. From this project, I will increase the features in determining housing prices in DC. 

The article, "Estimating Residential Property Values on the Basis of Clustering and Geostatistics" by Beata Calka, looks at clustering housing prices with K-means. The paper develops a 2 stage method to predicting housing prices in Poland. The first stage takes into account structural features to cluster the properties. This isolates "local property markets where properties have similar structural attributes." The second stage estimates the impact of the spatial factor (location) on property value by "performing an interpolation for each cluster separately using ordinary kriging (Gaussian process regression)." This results in property value maps, drawn up separately for each of the clusters. This article gives a lot of information on different ways to perform K-means clustering to predict prices. 

What are the Gaps?

DC Residential Properties has had limited analysis done past EDA besides limited machine learning models constructed on the dataset. Regression has been done with limited features, similar to the first literary review feedback and that is somewhere this project can improve upon. This project can also compare models which has not been done limited on this data set. This project will also include K-mean clustering which has not been done on this dataset and can add more dimension the overall analysis.  Broadly, predicting housing markets models has been performed on other markets but each market is unique and will not necessarily have the same important features. This project will also be able to produce a visual map on different features and prices of the housing market. 

Data Set:

The dataset I am using is called DC Residential Properties. It is aggregated from four different raw datasets. The first dataset is the Census Tracts 2010 data which includes selected geographic, cartographic and demographic data. The second dataset is Computer Assisted Mass Appraisal - Residential which includes attribution on housing characteristics for residential properties. The third dataset is the Computer Assisted Mass Appraisal- Condominium which includes attribution of housing characters for Condominium properties. The second and third datasets were created as part of the DC Geographic Information System for the DC office of Chief Technology Officer and participating DC government agencies. The last dataset is the address points that contain locations and attributes of Address points as of July 2018. This dataset is from the Master Address Repository for the DC Office of the Chief Technology Officer and DC Department of Consumer and Regulatory Affairs. 

Dataset Characteristics:

49 columns, 158955 rows, 52.81 MB

Dataset Sources:

DC Residential Properties Dataset: https://www.kaggle.com/christophercorrea/dc-residential-properties

Raw data:

Raw Census Tracts 2010 data: https://opendata.dc.gov/datasets/census-tracts-in-2010/explore

Raw Residential data: https://opendata.dc.gov/datasets/computer-assisted-mass-appraisal-residential/explore

Raw Condominium data: https://opendata.dc.gov/datasets/computer-assisted-mass-appraisal-condominium/explore

Raw Address Points data: https://opendata.dc.gov/datasets/address-residential-units/explore

Hypothesis / Research Question(s):

Which model can predict DC residential Housing Prices the most accurately?

What features are important to predicting DC Residential Housing Prices? 

Is it really all about Location? What are the most expensive locations?

Implementation (Model):

Part 1: Create predictive model for DC Residential Properties

-Linear Regression

-Decision Tree Model

-Random Forest Regressor Model

Part 2: Location of Housing Prices

-K-Means Clustering

-Create map to show different levels of housing prices

Cleaning Data

1. Used info(), describe(), and isnull().sum() to get an understanding of the columns, data type, and missing data.
2. Decided to delete columns Unnamed:0','NUM_UNITS','AYB','YR_RMDL','SALEDATE','SALE_NUM','GBA','USECODE','GIS_LAST_MOD_DTTM','CMPLX_NUM','LIVING_GBA','NATIONALGRID','ASSESSMENT_SUBNBHD','CENSUS_TRACT', 'CENSUS_BLOCK', and 'QUALIFIED' because they were not relevant for predicting and/ or they had to much missing data to be relevant
4. I noticed a common theme that Condominium data was missing so I decided to focus on residential and get rid of condominium rows
5. I decided to dropna() the rest of the missing data because it was mainly missing price data which is the target of the model
6. I also changed square footage from object to float64.
7. Used duplicates() and found no duplicated data
8. Used box plot to show “Price” and then used code to normalize outliers
9. Added unemployment rate based on ward
10. Made the column based on the unemployment rate data for each ward
Using in replacement for wards in the model
January 2019 unemployment data which lines up with current data

11. Add Dummy variables for Ward, Quadrant, AC, and Neighborhood

  
