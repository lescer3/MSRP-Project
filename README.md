# Predicting MSRP based on Car features 
The purpose of this project is to build a machine learning model to predict the Manufacturer's Suggested Retail Price (MSRP) of cars based on various features, such as make, year, and engine fuel type. 

## Technologies Used
- **Programming Languages**: R
- **Libraries**: dplyr, naniar, tidyr, ggplot2, forcats, corrplot, tidymodels, vip, patchwork, car, broom, stringr
- **Tools**: Git, GitHub

## Data
This project uses the Car Features and Prices Dataset from Kaggle provided by Rupinder Singh Rana, which includes approximately 12 thousand observations, 16 columns, and has 28 years of data from 1990 to 2017. Here are the following columns:

## Variables:
- Make: The company that produces the vehicle
- Model: The product name of the vehicle used by the manufacturer
- Year: The year the vehicle was made
- Engine.Fuel.Type: The type of fuel the vehicle uses
- Engine.HP: The engine's horse power 
- Engine.Cylinders: Number of cylinders 
- Transmission.Type: The type of transmission the vehicle has
- Driven_Wheels: The type of wheels the vehicle has 
- Number.of.Doors: The number of doors the vehicle has
- Market.Category: The classification of the vehicle
- Vehicle.Size: The size of the vehicle
- Vehicle.Style: Type of vehicle
- highway.MPG: How many miles a vehicle can travel on a gallon of gas while driving on the freeway
- city.MPG: How many miles a vehicle can travel on a gallon of gas while driving in the city
- Popularity: Popularity of the vehicle
- MSRP: Price of the vehicle in ($)
- Category: Whether a car is luxury or non-luxury
  
You can download the dataset from [Kaggle](https://www.kaggle.com/datasets/rupindersinghrana/car-features-and-prices-dataset).
*Note Category is not in the columns.

## Models
The project uses various models to predict the MSRP based on features such as make, model, year, engine specifications, and more. The following models were used:

### Stepwise Regression
Stepwise Regression was used to identify the most significant features for predicting car prices. The model was trained on several features including, 

- Make
- Model
- Year
- Engine fuel type
- Engine horsepower
- Engine cylinders
- Transmission type
- Driven wheels
- Market category
- Vehicle size
- Vehicle style
- City miles per gallon (MPG)
  
These features were selected after running backward selection combined with the Variance Inflation Factor (VIF) function to ensure multicollinearity was minimized. This method helped o avoid overfitting and improve the model's predictive power. 

### Lasso Regression
Lasso (Least Absolute Shrinkage and Selection Operator) regression was applied to shrink the less relevant coefficients towards zero, which allowed for feature selection and regularization. 

### Random Forest
Random forest, an ensemble method, was used to create multiple decision trees and combine their results. This model prevents overfitting due to the randomness in the tree building process. It also provided a measure of feature importance, helping to identify which variables are significant to the MSRP. 

### PCA Regression
PCA regression was used to reduce the dimensionality of the dataset. The original features were transformed into principal components that account for the largest variance in the data. The model was used to address multicollinearity and overfitting, it was then followed by a linear regression model, where the transformed features were used as predictors. 

## Results
Random forest was the model achieving the lowest Root Mean Square Error (RMSE) value of 5.79, indicating the best predictive power over the other models. Additionally, it provided valuable insights into the significant features, with year and engine horsepower as the most significant predictors for car prices.
