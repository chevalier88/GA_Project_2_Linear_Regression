# Ames Housing Regression Modelling

## Problem Statement

Can we help real estate agents in the city of Ames, Iowa predict the sale price of a house based on housing and real estate data using key predictors to create an accessible predictive Regression-based model?

## Executive Summary
The short answer is **yes**. After cleaning and exploring our datasets visually, we were able to uncover significant correlations between specific features of the Ames housing data set and their impact on price. The challenge was to be able to meaningfully map out an array of features that were not only continuous variables - we had to also analyze correlations between discrete variables and categorical features with housing prices.

The exploratory data analysis and visualizations suggested these general feature types as being most determinant over price:
- Features relating to area metrics e.g. `Gr Living Area`
- The quality and condition of the house e.g. `Overall Qual`
- The neighbourhood the home is situated i.e. `Neighborhood`
- Additional fixtures like fireplaces and basements e.g.`Fireplaces`
- When the house was constructed or remodeled e.g. `Year Built`.

However, due to the outliers and skewed data, select features had to be logarithmically transformed, including time-related features like `Yr Sold`. Categorical variables were one-hot encoded for machine readability, and during our pre-processing, we also standardized the scale of our model to further address skewed data. 

With feature engineering and scale standardization done, we them mounted the data onto Linear, Ridge and Lasso Regression models. We assessed regression metrics, and found that the baseline score of our Linear Regression model was accurate and robust enough to handle price prediction (Cross Validation Score of 0.83, R2 of 0.86 and Root Mean Squared Error of 33,569). It seemed that the right features getting selected had a better impact on price prediction over regularizing techniques, like Ridge and Lasso Regression. Both of those models had far worse metrics and were underfitted, so we did not choose them for our winning model.

## Methodology

- [Cleaning Train and Importing Data](https://git.generalassemb.ly/chevalier88/DSI15-Clone/blob/master/project_2/code/1.Cleaning_Imports.ipynb)
    - Data import
    - Data cleaning, data type correction, dropping unwanted or null data
    - Missing data imputation 
    
- [Exploratory Data Analysis and Preprocessing ](https://git.generalassemb.ly/chevalier88/DSI15-Clone/blob/master/project_2/code/2.EDA_Preprocessing.ipynb)
    - Summary Statistics and Distributions
    - Correlation matrices, heatmaps, paired plots
    - In depth analysis for features
    - Preprocessing and more data preparation

- [Modelling and Regularization](https://git.generalassemb.ly/chevalier88/DSI15-Clone/blob/master/project_2/code/3.Modelling_Conclusion.ipynb)
    - Applying feature selection
    - One-hot encoding 
    - Fitting features onto Linear, Ridge and Lasso Regression Models
    - Assessing regression metrics for best fit
    - Plotting residuals for predictive model evaluation
    - Concluding Remarks with Research

## Data Files and Dictionary
- [Datasets](https://git.generalassemb.ly/chevalier88/DSI15-Clone/tree/master/project_2/datasets)
- [Data Dictionary](https://git.generalassemb.ly/chevalier88/DSI15-Clone/blob/master/project_2/DataDocumentation.txt)

## Conclusion and Recommendations
We already know that our error variables are pretty good for the Linear Regression model.

The advantages of Linear Regression models are that they are easy to implement when data is linearly separable, but can be underfit when the data isn't. Thankfully, our cross-validations and feature selection have helpfully rendered bias and variance to low levels, but of course it comes at the cost of sophistication since we have reduced the relative types of features used to predict.

However, the dataset is limited, and the following data is absent:
- Economic Conditions and State Interest Rates
- More Neighbourhood Features e.g. Amenities, Facilities and Schools Nearby
- Data beyond 2006 - 2010
- Appearance/Architecture
- Investment Potential
- Energy-saving Features

If newer data can be supplied, the model can be even more useful. Real estate agents can then rely on our data as a benchmark, before applying their own professional judgement in assessing whether what their own inspections and research could add or subtract from our own predicted estimates.

In this way, our model, when combined with the professional judgement of our stakeholders, can be used to support them in their work by predicting prices.

## External Resources
https://www.zillow.com/ames-ia/home-values/
https://www.bestplaces.net/climate/city/iowa/ames 
https://weatherspark.com/y/10339/Average-Weather-in-Ames-Iowa-United-States-Year-Round 
https://www.finder.com.au/what-influences-a-propertys-value