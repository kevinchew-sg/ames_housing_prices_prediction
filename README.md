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
|---|---|
|**Linear Regression**|No|Original|728884276.23|
|**Ridge Regression**|No|Original|688259031.27|
|**Lasso Regression**|No|Original|693984536.72|


|Feature|Coefficient|
|---|---|
|**MS SubClass**| 2762.334115018486
|**MS Zoning**| 3444.101134308963
|**Lot Area**| 7049.022926803096
|**House Style**| 2258.877261166752
|**Overall Qual**| 10189.745212580223
|**Mas Vnr Type**| -2872.359398886125
|**Mas Vnr Area**| 6517.216967297893
|**Exter Qual**| 9445.41974852496
|**Foundation**| 2056.5696717784595
|**Bsmt Qual**| 3641.893387541233
|**Bsmt Cond**| -4370.125422607394
|**Bsmt Exposure**| 4764.001038748247
|**BsmtFin Type 1**| -198.35462274964084
|**BsmtFin SF 1**| 8505.167066962458
|**Total Bsmt SF**| 6733.717456395505
|**Heating QC**| 2350.798460365768
|**1st Flr SF**| 2432.170589340036
|**Gr Liv Area**| 19562.711834955742
|**Bsmt Full Bath**| 3036.339355477903
|**Kitchen Qual**| 11170.488236014004
|**Fireplace Qu**| 1503.015422101831
|**Garage Type**| -764.4464538275497
|**Garage Finish**| 1241.1812351671979
|**Garage Area**| 5587.376255501178
|**Wood Deck SF**| 1737.833282800886
|**Open Porch SF**| 1572.6942696925835
|**Neighborhood_BrkSide**| 11417.550730271476
|**Neighborhood_CollgCr**| -4341.114056193408
|**Neighborhood_Crawfor**| 18799.545710284467
|**Neighborhood_Edwards**| -1884.1952654389606
|**Neighborhood_Gilbert**| -3016.3225623015023
|**Neighborhood_MeadowV**| -15657.21565416412
|**Neighborhood_NWAmes**| -3445.474813470146
|**Neighborhood_NoRidge**| 20181.452181746296
|**Neighborhood_NridgHt**| 27920.043800807733
|**Neighborhood_Sawyer**| 3609.748134014415
|**Neighborhood_SawyerW**| -7134.123810850086
|**Neighborhood_Somerst**| 7118.328333539481
|**Neighborhood_StoneBr**| 39188.12787274329
|**Neighborhood_Timber**| 5353.374746174013
|**Exterior 1st_BrkFace**| 16026.755824373366
|**Exterior 1st_CemntBd**| 20308.9053170126
|**Exterior 1st_MetalSd**| 2586.4691869386006
|**Exterior 1st_VinylSd**| 6216.936273453408
|**Exterior 1st_Wd Sdng**| -8709.567873435095
|**Exterior 2nd_AsbShng**| -13357.450957017441
|**Exterior 2nd_Plywood**| -530.9545989684993
|**Exterior 2nd_Stucco**| -5709.417014205799
|**Exterior 2nd_Wd Sdng**| 8824.665260812748


## Conclusion

### Location is King

As expected, the location of the house is a big factor in determining how much the house can sell for. The largest numerically coeffcients all belong to 'Neighborhood', which means that for some neighborhoods, homeowners will be able to fetch a much higher price compared to other locations. 


### Size is important too

Moreover, as one would expect, a bigger house is more likely to fetch a higher price. Be it the lot area, masonry veneer area or basement area etc, they all show an average to large positive coefficient in relation to the the price of the house.  Moreover, what our model aims to achieve is to provide a reference to home owners on the fair price that their houses can sell for, and more importantly, a guide to what they can do to increase that price.

### Maintaining or improving Quality of houses

Nevertheless,  what our model aims to achieve is to provide a reference to home owners on the fair price that their houses can sell for, and more importantly, a guide to what they can do to increase that price.
Homeowners should always look to improve or maintain the quality of the different aspects of their houese, such as kitchen, basement, exterior etc. Putting ourselves in the buyers' shoes, we are much less willing to pay a premium price for a house that requires renovation or repair since these require cost. 
Moreover, homeowners can use our model to evaluate whether the upgrading cost is worth financially or not. For example, the coefficient for Kitchen Qual is 10543.35. Should the upgrading cost be less than $10,000 , we would say that it is worth it.


#### Exterior of the house matters
Furthermore, the exterior of the house is another important factor too. For example, should the exterior covering be Asbestos Shingles, this will severly bring down the price. This makes sense as prolonged asbestos exposure could lead to an increase in likelihood of contracting cancer. Thus, a homeowner could consider changing the exterior of the house, but only if the cost is lower than the coefficient.


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













