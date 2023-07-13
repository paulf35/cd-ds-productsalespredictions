# Prediction of Product Sales
**Author**: Paul Foy

# Business Problem
Big Mart stores need help predicting sales figures for specific items across their vast network of outlet stores. Predicting accurate sales figures has been a challenge for this client. This project will help Big Mart determine how to restock items and anticipate demand in a more agile way. 

# Data Source
Analytics Vidhya - Big Mart Sales Prediction: https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view?usp=sharing

For this dataset, there are 8,523 rows and 12 columns.

## Data Dictionary
| Variable Name | Description |
|---------------|-------------|
| Item_Identifier |	Product ID|
| Item_Weight |	Weight of product |
| Item_Fat_Content |	Whether the product is low-fat or regular |
| Item_Visibility |	The percentage of total display area of all products in a store allocated to the particular product |
|Item_Type |	The category to which the product belongs |
| Item_MRP | Maximum Retail Price (list price) of the product |
| Outlet_Identifier	| Store ID |
| Outlet_Establishment_Year |	The year in which store was established |
| Outlet_Size |	The size of the store in terms of ground area covered |
| Outlet_Location_Type | The type of area in which the store is located |
| Outlet_Type |	Whether the outlet is a grocery store or some sort of supermarket |
| Item_Outlet_Sales |	Sales of the product in the particular store. This is the target variable to be predicted. |

# Data Preperation
To prepare this data, the following processes were performed:

## Exploratory Data Analysis Performed:
During the Exploratory Data Analysis stage, we created the following visuals:
- A histogram for each numerical feature.
- Boxplots to view statistical summaries of numerical features.
- Countplots to view the frequency of each class of categorial features.
- A heatmap to view the correlation between features.
  
## Key Insights:
1. When looking at the distrubtion of item types, Fruits and Vegetables has the higest count. Seafood has the lowest count.
   
![EDA-ItemType-CountPlot](https://github.com/paulf35/cd-ds-productsalespredictions/assets/133720473/7b16e80b-9923-4454-b695-d5cecd8049a0)

3. There are more low-fat items then regular-fat items. 
   
![image](https://github.com/paulf35/cd-ds-productsalespredictions/assets/133720473/2dc5a5c6-fa0e-4afa-915c-a69b177ab0e1)

# Explantory Visuals

1. The most common item type is 'Fruits and Vegetables,' which occurs 1,232 times (14.46%) in the dataset. 

![Count-Item-Type](https://github.com/paulf35/cd-ds-productsalespredictions/assets/133720473/d5f55c33-265a-4e81-bcdf-4c5b099d7800)

2. The most common outlet size is 'Medium', which occurs 2,793 times (32.77%) in the dataset. 

![EDA-OutletSize](https://github.com/paulf35/cd-ds-productsalespredictions/assets/133720473/1d60482e-7533-46c3-8b9d-e76b30298d6d)

# Machine Learning Modeling and Evaluation
Below is a list of all three models tested: 
- Linear Regression Model
- Random Forest Model
- Tuned Random Forest model

The tables below sow the MAE, MSE, RSME, and R^2 results for each model tested. 

**Default Linear Regression Model:**
|     | MAE  | MSE | RMSE | R^2 |
|-----|-------|-----------|--------|-----|
|Train|847.663|1298669.325|1139.592|0.561|
|Test| 810.386 |1210321.266 | 1100.146 | 0.568 |

**Default Random Forest Model:**
|	    |MAE    |	MSE	      | RMSE   |	R^2 |
|-----|-------|-----------|--------|-----|
|Train |296.841 |	182957.964 |	427.736 |	0.938 |
|Test |	778.649 |	1249723.025 |	1117.910 |	0.554 |

**Tuned Random Forest Model:**
|	    |MAE    |	MSE	      | RMSE   |	R^2 |
|-----|-------|-----------|--------|-----|
|Train |637.369	| 806900.857 | 898.277 | 0.727
|Test |	748.389 |	1154142.731 |	1074.310 |0.588

Based on the results detailed in the **Model Evaluation and Results** section, the Default Linear Regression model performed the best out of the three models. The MAE value for the Test data was `$810.39`, which is an acceptable range and similar the MAE value of the train data. RMSE results show a similar trend. On the Test data, the RMSE value sas '$1,100.15`, which is in an acceptable range and similar to the RMSE value in the Training set. 

R^2 values are low, which shows there is bias in the model. The R^2 value for the Test dataset is `56.8%`. Ideally, we'd want this value to be higher, but because it's similar to the Train R^2 value (`56.1%) means there only a slight underfit. 

## Recommendation
Based on the results I recommend that we **DO NOT** deploy any of the tested models. I recommend that we continue tuning the existing linear regression model in order to increase the R^2 value, while optimizing for low bias and variance. We should also test additionl models. Additionally, in future models, I recommend that we add additional ddata and features that might be helpful, as well as remove any features that aren't needed.  
