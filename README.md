# Restaurant-Profit-Growth-Prediction
Predict restaurant profit growth using factors such as location, local population, and drive-thru availability.

## Summary

This project predicts whether a restaurant will achieve profitability within three years by analyzing a dataset with 1,090 rows and 8 features related to site selection. Through exploratory data analysis and model fitting, key factors influencing profitability are identified, and a predictive model is developed to forecast future profits.

## Data Validation

We have validated all variables in the dataset, and the following changes have been made:
1. 'location': Validated to ensure uniqueness.
2. 'year_3_profit': This feature serves as the target variable and has not been changed.
3. 'local_pop': This feature contained 'Unknown' values that have been replaced with the mean of the data.
4. 'competitors': No changes have been made; validation confirmed it as a positive integer.
5. 'nearest_fgh': No changes have been made; validation confirmed it as a positive integer.
6. 'hours': Since this is ordinal data, it has been mapped to preserve the order. Empty hours have been substituted with the most frequent data.
7. 'highway': Negative values have been replaced with the mean to comply with the requirement of a minimum time of one minute.
8. 'drivethru': As an ordinal feature, 'No drivethru' has been replaced with 'No,' and the data has been transformed into binary (0 and 1).

## Exploratory Analysis

We have created single and multiple variable graphs to better understand the dataset. Here are our findings:
1. There are many outliers in the 'nearest_fgh' feature.
2. The median distance from the FGH restaurant to the highway is approximately 15.
3. Stores with extended hours appear to be more profitable.
4. Drive-thru establishments seem to generate more profit than those without a drive-thru.
5. Stores without competitors and with higher local populations seem to be more profitable.

## Model Fitting & Evaluation

We aim to predict a categorical outcome with two classes (0 or 1). We have chosen logistic regression as the baseline and random forest as our comparison model because the relationship between features and the target variable is nonlinear and complex, and the dataset is imbalanced. We have addressed class imbalance by selecting appropriate sampling techniques. We plotted the feature importance to understand which features have a more significant impact on profitability.

## Model Evaluation

Logistic Regression vs Random Forest:
1. Random Forest is an ensemble learning method that combines multiple decision trees, reducing overfitting compared to individual decision trees. 
2. The accuracy of logistic regression is 60%, while the random forest achieves 78.5%.
3. The random forest exhibits better precision, recall, and F1 score.

## Metric for Business Monitoring

We should monitor model accuracy, precision, recall, and F1 score, as well as the importance of the features on which the target variable depends.

## Recommendations

- The random forest model can be used to assess the profitability of a new restaurant, as it predicts with an accuracy of 78%.

- The features have dependencies on local_pop (0.31), highway (0.25), and nearest_fgh (0.24). Choose a location with a higher local population, proximity to the highway, and greater distance from other FGH stores. Additionally, stores with extended hours,drivethru tend to be more profitable.

- Continuously improve the model by collecting more data, performing feature engineering, and fine-tuning parameters.

  
## Conclusion

This project shows that the random forest model can be employed to evaluate a restaurant site's profitability, with the local population, proximity to the highway, and distance from other FGH stores being the crucial factors to consider. By regularly monitoring business metrics, we can improve the model's accuracy and make better decisions about restaurant sites in the future.
