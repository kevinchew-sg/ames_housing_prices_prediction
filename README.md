# Housing-Price-Prediction

## Introduction

This project aims to create and refine a regression model that predicts the price of a house at sale at the Ames housing area. Ames is a city in Iowa, United States and is best known as the home of Iowa State University.

To create this regression model, we are given the Ames Housing Dataset, which contains several columns of different features relating to houses. Examples of such features are Garage Area, Kitchen Quality etc.

## Problem Statement

Our goal is to determine what are the most important features in determining the price of the house. In addition, by using our regression model, home owners who are looking to sell can determine if the offered price is fair or not. If the price do not meet expectations, the home owners can then focus on upgrading these features to drive up the price of the house. We will be using mean squared error to evaluate our models.

## Outline

* **Section 1: Understanding our Data**
    * Importing of libraries and datasets, and a quick review of the datasets
* **Section 2: Data Cleaning**
    * Handling Outliers and Null values observed in the datasets
* **Section 3: Dropping Columns/Features**
    * Exploratory Data Analysis is done to conduct the first round of dropping. Additional features are dropped later after further analysis
* **Section 4: Feature Engineering**
    * Feature engineering is done on categorical columns/features to prepare for modeling
* **Section 5: Selected Features for modeling**
    * Finalised list of features to conduct first iteration of modeling
* **Section 6: Model Fitting**
    * First round of model fitting is done
* **Section 7: Fine-tuning of Model**
    * Second round of model fitting is done
* **Section 8: Conclusion**
    * Findings are shared in this section
* **Section 9: Kaggle Prediction**
    * Model is used to predict prices of houses in the test dataset


## Main Findings

From our initial model fitting, we learnt that Ridge and Lasso Regression gives us better results as compared to Linear Regression. We then did a round of fine-tuning, whereby we used the coefficients of our Lasso Regression to fine tune our selection of variables and run another round of model fitting. We had found the best model to be Ridge Regression. 
This makes sense as Ridge Regression is a technique for analyzing multiple regression data that suffer from multicollinearity, which is prevalent in this dataset. 



### Models Findings
|Model|Mean Squared Error|
|---|---|---|---|
|**Linear Regression**|No|Original|728884276.23|
|**Ridge Regression**|No|Original|688259031.27|
|**Lasso Regression**|No|Original|693984536.72|


|Feature|Coefficient|
|---|---|
|**MS SubClass**|4461.87|
|**MS Zoning**|4261.17|
|**Lot Area**|5681.13|
|**House Style**|1041.61|
|**Overall Qual**|10812.66|
|**Mas Vnr Type**|-3592.6|
|**Mas Vnr Area**|7130.45|
|**Exter Qual**|10356.70|
|**Foundation**|1812.14|
|**Bsmt Qual**|3344.66|
|**Bsmt Cond**| -4326.41
|**Mas Vnr Type**|-3592.6|
|**Bsmt Exposure**| 4788.13
|**BsmtFin Type 1**| -619.02
|**BsmtFin SF 1**| 10053.50
|**Total Bsmt SF**| 5812.22
|**Heating QC**| 2802.45
|**1st Flr SF**| 3552.75
|**Gr Liv Area**| 19304.56
|**Bsmt Full Bath**| 2056.48
|**Kitchen Qual**| 10543.35
|**Fireplace Qu**| 1477.75
|**Garage Type**| -358.78
|**Garage Finish**| 1048.57
|**Garage Area**| 5782.66
|**Wood Deck SF**| 1692.58
|**Open Porch SF**| 1377.62
|**Neighborhood_BrkSide**| 10499.47
|**Neighborhood_CollgCr**| -3601.32
|**Neighborhood_Crawfor**| 17510.97
|**Neighborhood_Edwards**| -2156.76
|**Neighborhood_Gilbert**| -27.14
|**Neighborhood_MeadowV**| -9787.41
|**Neighborhood_NWAmes**| -1930.80
|**Neighborhood_NoRidge**| 20554.42
|**Neighborhood_NridgHt**| 29190.88
|**Neighborhood_Sawyer**| 3706.38
|**Neighborhood_SawyerW**| -5591.50
|**Neighborhood_Somerst**| 8742.77
|**Neighborhood_StoneBr**| 41662.88
|**Neighborhood_Timber**| 1535.87
|**Exterior 1st_BrkFace**| 15857.38
|**Exterior 1st_CemntBd**| 16453.18
|**Exterior 1st_MetalSd**| 3539.08
|**Exterior 1st_VinylSd**| 5861.59
|**Exterior 1st_Wd Sdng**| -9306.65
|**Exterior 2nd_AsbShng**| -2972.72
|**Exterior 2nd_Plywood**| 26.96
|**Exterior 2nd_Stucco**| -1190.60
|**Exterior 2nd_Wd Sdng**| 10739.24
|Neighborhood_Veenker|43854.60

## Conclusion

### Location is King

As expected, the location of the house is a big factor in determining how much the house can sell for. The largest numerically coeffcients all belong to 'Neighborhood', which means that for some neighborhoods, homeowners will be able to fetch a much higher price compared to other locations. 


### Size is important too

Moreover, as one would expect, a bigger house is more likely to fetch a higher price. Be it the lot area, masonry veneer area or basement area etc, they all show an average to large positive coefficient in relation to the the price of the house.  Moreover, what our model aims to achieve is to provide a reference to home owners on the fair price that their houses can sell for, and more importantly, a guide to what they can do to increase that price.

### Maintaining or improving Quality of houses

Nevertheless,  what our model aims to achieve is to provide a reference to home owners on the fair price that their houses can sell for, and more importantly, a guide to what they can do to increase that price.
Homeowners should always look to improve or maintain the quality of the different aspects of their houese, such as kitchen, basement, exterior etc. Putting ourselves in the buyers' shoes, we are much less willing to pay a premium price for a house that requires renovation or repair since these require cost. 
Moreover, homeowners can use our model to evaluate whether the upgrading cost is worth financially or not. For example, the coefficient for Kitchen Qual is 10543.35. Should the upgrading cost be less than $10,000 , we would say that it is worth it.



## Data Dictionary


|S/N|Numeric Feature|Data Type|
|---|---|---|
|1|**Lot Area**|Continuous|
|2|**Mas Vnr Area**|Continuous|
|3|**BsmtFin SF 1**|Continuous|
|4|**BsmtFin SF 2**|Continuous|
|5|**Bsmt Unf SF**|Continuous|
|6|**Total Bsmt SF**|Continuous|
|7|**1st Flr SF**|Continuous|
|8|**2nd Flr SF**|Continuous|
|9|**Low Qual Fin SF**|Continuous|
|10|**Gr Liv Area**|Continuous|
|11|**Bsmt Full Bath**|Discrete|
|12|**Bsmt Half Bath**|Discrete|
|13|**Full Bath**|Discrete|
|14|**Half Bath**|Discrete|
|15|**Bedroom AbvGr**|Discrete|
|16|**Kitchen AbvGr**|Discrete|
|17|**TotRms AbvGrd**|Discrete|
|18|**Fireplaces**|Discrete|
|19|**Garage Cars**|Discrete|
|20|**Garage Area**|Continuous|
|21|**Wood Deck SF**|Continuous|
|22|**Open Porch SF**|Continuous|
|23|**Enclosed Porch**|Continuous|
|24|**3Ssn Porch**|Continuous|
|25|**Screen Porch**|Continuous|
|26|**Pool Area**|Continuous|
|27|**Misc Val**|Continuous|
|28|**MS SubClass**|Nominal|
|29|**MS Zoning**|Nominal|
|30|**Street**|Nominal|
|31|**Lot Shape**|
|32|**Land Contour**|Nominal|
|33|**Utilities**|Ordinal|
|34|**Lot Config**|Nominal|
|35|**Land Slope**|Ordinal|
|36|**Neighborhood**|Nominal|
|37|**Condition 1**|Nominal|
|38|**Condition 2**|Nominal|
|39|**Bldg type**|Nominal|
|40|**House Style**|Nominal|
|41|**Overall Qual**|Ordinal|
|42|**Overall Cond**|Ordinal|
|43|**Roof Style**|Nominal|
|44|**Roof Matl**|Nominal|
|45|**Exterior 1st**|Nominal|
|46|**Exterior 2nd**|Nominal|
|47|**Mas Vnr Type**|Nominal|
|48|**Exter Qual**|Ordinal|
|49|**Exter Cond**|Ordinal|
|50|**Foundation**|Nominal|
|51|**Bsmt Qual**|Ordinal|
|52|**Bsmt Cond**|Ordinal|
|53|**Bsmt Exposure**|Ordinal|
|54|**BsmtFin Type 1**|Ordinal|
|55|**BsmtFin Type 2**|Ordinal|
|56|**Heating**|Nominal|
|57|**Heating QC**|Ordinal|
|58|**Central Air**|Nominal|
|59|**Electrical**|Ordinal|
|60|**Kitchen Qual**|Ordinal|
|61|**Functional**|Ordinal|
|62|**Fireplace Qu**|Ordinal|
|63|**Garage Type**|Nominal|
|64|**Garage Finish**|Ordinal|
|65|**Garage Qual**|Ordinal|
|66|**Garage Cond**|Ordinal|
|67|**Paved Drive**|Ordinal|
|68|**Id**|Discrete|
|69|**PID**|Nominal|
|70|**Sale Type**|Nominal|
|71|**Mo Sold**|Discrete|
|72|**Year Built**|Discrete|
|73|**Yr Sold**|Discrete|
|74|**Garage Yr Blt**|Discrete|
|75|**Year Remod/Add**|Discrete|
|76|**Pool QC**|Ordinal|
|77|**Misc Feature**|Nominal|
|78|**Alley**|Nominal|
|79|**Fence**|Ordinal|
|80|**Lot Frontage**|Continuous|
|81|**SalePrice**|Continuous|













