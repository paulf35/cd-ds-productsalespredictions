# Prediction of Product Sales
**Author**: Paul Foy

# Business Problem: 
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
- Boxplots to view statistical summaries of numerical features
  Countplots to view the frequency of each class of categorial features.
- A Heatmap to view the correlation between features.
  
## Key Insights:
1. When looking at the distrubtion of Item types, Fruits and Vegetables has the higest count. Seafood has the lowest count.
   
![EDA-ItemType-CountPlot](https://github.com/paulf35/cd-ds-productsalespredictions/assets/133720473/7b16e80b-9923-4454-b695-d5cecd8049a0)

3. Average weights across all item types are very similar
   
![EDA-Item_Type-BoxPlot](https://github.com/paulf35/cd-ds-productsalespredictions/assets/133720473/14c7cc8c-21f2-4b7a-91c3-1be9a5c900f7)

# Explantory Visuals

1. The most common item type is Fruits and Vegetables, which occurs 1,232 times (14.46%) in the dataset. 

![Count-Item-Type](https://github.com/paulf35/cd-ds-productsalespredictions/assets/133720473/d5f55c33-265a-4e81-bcdf-4c5b099d7800)

2. The most common Outlet Size is 'Medium', which occurs 2,793 times (32.77%) in the dataset. 

![EDA-OutletSize](https://github.com/paulf35/cd-ds-productsalespredictions/assets/133720473/1d60482e-7533-46c3-8b9d-e76b30298d6d)

# Machine Learning Modeling and Evaluation

## Evaluated Models
- Linear Regression Model
- Random Forest Model
- Tuned Random Forest model

## Model Evaluations and Results
**Linear Regression Model:**
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

# Recommendations

Based on the results, the best performing model of the ones I evaluated was the Tuned Random Forest model.
 - For the Tuned Random Forest model 58.8% of the variance in y was explained by x.
 - The Mean Absolute Error was off by $748.389.
 - The Mean Squared Error was $1,154,142.73.
 - The Root Mean Squared Error was $1074.31

While this model was the most performant of the ones tested, using this model to accurately predict sales would not be very reliable. The R^2 value is low (58.8%), so there is some bias in model. The Mean Squared Error value is also very high, which could make the model less than optimal. 
