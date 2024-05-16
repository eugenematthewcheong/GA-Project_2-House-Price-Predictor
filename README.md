<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 2: Model for Predicting House Evaluation Prices

> Authors: Lim Zheng Gang, Eugene Matthew Cheong, Pius Yee

## Goals
Creating a model to help empower our agents to provide customers invaluable insights for making well-informed decisions on pricing of houses.

## Problem Statements
Our current manual process of evaluating property data for customers is time-consuming and prone to inconsistencies, as it relies on individual agents generating analyses independently. 

To address this challenge, we have developed a model for this project, aimed at empowering our agents to deliver consistent property evaluations to customers. 

By leveraging this model, our agents can provide invaluable insights and make data-driven decisions, ensuring a standardized approach to property valuation.

## Dataset

HDB resale transaction data - sourced from GA

Supermall location (longitutde and latitude) - data extracted from HDB resale transaction data

## Data Dictonary
##### *(i) General features*


|Feature|Type|Dataset|Description|
|---|---|---|---|
|id|int64|train.csv|Transaction ID for HDB resale|
|resale_price|float64|train.csv|Resale price of the HDB transaction|
|mid|int64|train.csv|Middle floor from the range of floor level|
|floor_area_sqft|float64|train.csv|Floor size of the HDB flat|
|max_floor_lvl|int64|train.csv|Max floor level for the block of transacted unit|

##### *(ii) Distance related features*


|Feature|Type|Dataset|Description|
|---|---|---|---|
|mrt_nearest_distance|float64|train.csv|Distance to the nearest MRT|
|from_centre_distance|float64|train.csv|Distance from Central area. GA campus set as the central area|
|mh|float64|sm_location_supermalls.csv|Distance to supermall i.e. the popular malls with very high number of customers|

##### *(iii) Planning Area related features*


|Feature|Type|Dataset|Description|
|---|---|---|---|
|mature|int64|train.csv|Mature HDB estate|
|planning_area_category_Group1|int64|train.csv|Includes areas such as Tanglin, Bukit Timah, Outram, Downtown Core, Bishan.|
|planning_area_category_GroupA|int64|train.csv|Includes areas such as Ang Mo Kio.|
|planning_area_category_GroupCM|int64|train.csv|Includes areas such as Marine Parade, Changi. |
|planning_area_category_GroupCQS|int64|train.csv|Includes areas such as Queenstown, Serangoon, Clementi.|
|planning_area_category_GroupJB|int64|train.csv|Includes areas such as Bukit Merah, Jurong East.|
|planning_area_category_GroupPWC|int64|train.csv|Includes areas such as Bukit Panjang, Choa Chu Kang, Woodlands.|
|planning_area_category_GroupYH|int64|train.csv|Includes areas such as Hougang, Yishun.|

##### *(iv) Time related features*


|Feature|Type|Dataset|Description|
|---|---|---|---|
|tenure|int64|train.csv|Transaction year less lease commencement year|
|tenure_buckets_0-10|int64|train.csv|Tenure bucket for 0 to 10 years|
|year_category_Group0|int64|train.csv|Year categories by the resale price trend. Group 0 is the years with lowest avg resale price|
|year_category_Group1|int64|train.csv|Year categories by the resale price trend. Group 1 is the years with 2nd lowest avg resale price|
|year_category_Group2|int64|train.csv|<Year categories by the resale price trend. Group 0 is the years with 2nd highest avg resale price>|
|is_pre_war|int64|train.csv|Flat built before war i.e. 1949|

##### *(v)Flat types related features*


|Feature|Type|Dataset|Description|
|---|---|---|---|
|is_premium|int64|train.csv|Flat model is DBSS or Improved-Maisonette|
|is_terrace|int64|train.csv|Landed terrace HDB|
|is_superlargeterrace|int64|train.csv|Terrace with size more than 2250 sqft|
|flat_type_1 ROOM|int64|train.csv|1-room flat|
|flat_type_2 ROOM|int64|train.csv|2-room flat|

## Methodology
### *Notebook 1*
Data cleaning and EDA

### *Notebook 2*
Feature engineering and selection

### *Notebook 3*
Model selection - Linear regression, Ridge Regression and Lasso Regression

### *Notebook 4*
Kaggle submission

## Findings
Lasso Regression was chosen for the model because it achieved the best performance including R-squared score (0.0903) and RMSE (around $45,000).

## Conclusion and recommendation
It is highly recommended to use our model for HDB resale price prediction. 

Through extensive research and experimentation, our model achieves an R-squared score of 90.3%, indicating it can predict up to 90.3% of the variation in HDB resale prices. On average, the predicted price differs from the actual price by around $45,000 (RMSE).