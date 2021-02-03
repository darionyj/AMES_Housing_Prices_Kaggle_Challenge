# Project 2: Ames Housing Data and Kaggle Challenge


## Problem Statement
In this project, I will be building a model that predicts the price of a property on sale in Ames, Iowa. I will analyze the data to find the theoretical relationship between the features and sale price. There might be specific interest in the magnitudes and sign of the coefficients. By understanding each features using visualization and feature selections, a deeper insight can be gained for building a model.
This model will be able to assist stakeholders such as the buyers or sellers of the properties or developers who are looking to develop an area in a certain neighborhood. They will be able to negotiate at a better price with each other during a transaction or a deal and achieve a win-win situation.


## Executive Summary
Two set of data will be used for this project. One of them is the train dataset which is for model building, the other is the test data which is used for the predictions submissions. The train dataset will be used for EDA, cleaning, sorting and feature engineering. Once the train dataset features are ready, the test dataset features will be tallied against it. After completion of EDA and cleaning, the train dataset will be used to build the best model using four different methods. Then, the test dataset will be used to predict the submission with the best model built. This project will be seperated into two notebooks. First notebook is indicating the first part which EDA, cleaning and feature engineering happen. Second notebook will be the second part, containing the building of the model and predictions.

## Contents:

1. [Datasets Used](#1-Datasets-Used)
2. [Data Dictionary](#2-Data-Dictionary)
3. [Exploratory Data Analysis & Data Cleaning](#3-Exploratory-Data-Analysis-&-Data-Cleaning)
4. [Modeling for Predictions](#4-Modeling-for-Predictions) 
5. [Submission and Conclusions](#5-Submission-and-Conclusions)
6. [Python Library Used](#6-Python-Library-Used)

### 1. Datasets Used
The following datasets were used for this project:
- train
- test

The following datasets were created and used during this project:
- train_cleaned (train data after cleaning)
- test_cleaned (test data after cleaning)
- submission_final (data used for kaggle submission)

### 2. Data Dictionary
 
The data dictionary for datasets train and test is in this link: http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

Below is the data dictionary containing all the data features for train_cleaned:

|Feature|Type|Description|  
|:---:|:---:|:---:|
|lot frontage|float|Lot Frontage|
|lot area|int|Lot Area|  
|overall qual|int|Overall Quality| 
|mas vnr area|float|Masonry Veneer Area|
|exter qual|int|Exterior Quality|  
|bsmt qual|int|Basement Quality|  
|bsmt exposure|int|Basement Exposure|  
|bsmtfin type 1|int|Type 1 Basement Finished Area Rating| 
|total bsmt sf|float|Total Square Feet of Basement Area|
|heating qc|int|Heating Quality and Condition|
|gr liv area|int|Above Grade (Ground) Living Area Square Feet|
|kitchen qual|int|Kitchen Quality|
|totrms abvgrd|int|Total Rooms Above Grade| 
|fireplaces|int|Number of Fireplaces| 
|fireplace qu|int|Fireplace Quality|  
|garage finish|int|Interior Finish of Garage|  
|garage cars|float|Size of Garage in Car Capacity|
|garage area|float|Size of Garage in Square Feet|
|garage qual|int|Garage Quality|  
|garage cond|int|Garage Condition|  
|wood deck sf|int|Wood Deck Area in Square Feet|  
|saleprice|int|Sale Price|  
|ms subclass_60|uint|Dwelling Type(2-story 1946 & Newer)|
|ms zoning_RM|uint|Zoning(Residential Medium Density)|
|neighborhood_NoRidge|uint|Neighborhood(Northridge)|  
|neighborhood_NridgHt|uint|Neighborhood(Northridge Heights)| 
|neighborhood_StoneBr|uint|Neighborhood(Stone Brook)|  
|roof style_Hip|uint|Roof Style(Hip)|  
|exterior 1st_VinylSd|uint|Exterior Cover 1(Vinyl Siding)|  
|exterior 2nd_VinylSd|uint|Exterior Cover 2(Vinyl Siding)|  
|foundation_CBlock|uint|Foundation(Cinder Block)|  
|foundation_PConc|uint|Foundation(Poured Concrete)|  
|sale type_New|uint|Type of Sale(Newly Constructed)|  
|lot shape_Reg|uint|Shape of Property(Regular)|  
|mas vnr type_BrkFace|uint|Masonry Veneer Type(Brick Face)|  
|mas vnr type_None|uint|Masonry Veneer Type(None)|  
|mas vnr type_Stone|uint|Masonry Veneer Type(Stone)|
|garage type_Attchd|uint|Garage Location(Attached to home)|  
|garage type_Detchd|uint|Garage Location(Detached from home)|  
|bldg age|int|Age of the building since built|  
|bldg remod age|int|Age of the building since remodel|  
|garage age|float|Age of the garage since built|
|total bath|float|Number of bathrooms|

### 3. Exploratory Data Analysis & Data Cleaning
In this section,studying and understanding of the train data is being done. The following are the actions taken:
 - Errors and outliers in data have been identified and dealt with. 
 - Plot count plots for nominal features to study each feature. Dropping feature with very one-sided value
 - Studying and filling nominal features' null values 
 - One-Hot encoding on nominal features
 - Studying and filling ordinal features' null values
 - Binarization for ordinal features
 - Create new features to replace time-sensitive features
 - Studying and filling continuous features' null values
 - Finding multicollinearity between different features
 - Further feature engineering to combine features together 
 - Using heatmap to look for the correlations between all features and dropping low correlation features
 - Clean the test data features accordingly to the train data features
 
 
 ### 4. Modeling for Predictions 
In this section, I used lasso regression model to find the zero co-efficients predictors and remove them from the data. After that, I built the model based on four different methods. After building, I compared the R2 and RMSE scores between the four methods. Lasso regression is bested the other three methods.

### 5.  Submission and Conclusion
So out of the four methods, I have used lasso regression model as the model for predictions. After cleaning the test data again, I use it to predict and create a submission dataset. I used the dataset to submit to kaggle and gotten 31699 as my public score.

Key takeaways from the Project:

- There were alot of null values. I have cleaned them up by understanding the reason behind the null values. It can be related to other features in the same category, such as null values in misc features and how it is linked to misc values.

- Certain features are correlated and can form multicollinearity between them. Examples are total basement square feet, basement unfinished square feet, basement type 1 square feet, and basement type 2 square feet.

- From the data exploration and modeling using lasso regression, I have found out several different features have different impact on the price. Such as ground living area, overall quality and total basement surface are very positively correlated with the sale price. Age seems to have a huge impact on the price as well, as when a property get older, the price will get lower.

Limitations:

- Despite having strong correlation or multicollinerity between the features, dropping some of them may have affected the model.

Additionally, more could be done to improve the model. As I have only worked with Linear,Lasso,Ridge and Elastic Net model for this project, other models might be a better fit. Other features of properties can be included as well to better improve the model such as cost of constructing or remodelling the property, nearest public transportation in terms of distance or how many times the property have been switched hands.

### 6. Python Library Used
- Numpy
- Pandas
- MatplotLib
- Seaborn
- Sklearn
