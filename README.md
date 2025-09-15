# Air-Quality-Forecasting-with-Random-Forest-and-KNN-Regression
This project analyzes air quality data from the AirQualityUCI data set provided by the UCI Machine Learning Repository to predict pollutant concentrations and assess overall air quality levels using machine learning methods.

The data set includes hourly measurements of air pollutants (CO, NO2, O3), along with meteorological variable such as humidity and temperature collected from 2004-2005 in a small Italian city. Data preprocessing steps include removing missing values, correcting time/date formatting, and engineering features for analaysis.

Features used after preprocessing:
1. Temperature (°C)
2. Relative Humidity (RH) (%)
3. Absolute Humidity (AH)
4. Hour
5. Month
6. CO Concentration (mg/m³)
7. NO2 Concentration (µg/m³)
8. O3 Concentration (µg/m³)
9. C6H6 Concentrations
10. NOx Concentrations
11. PT08 (Applied to all pollutants to return an hourly sensor reading for each pollutant)

The models were seperated into three KNN-Regression models which each predicted AQI values by using different features.
1. Model 1: Predicted AQI values over time using Pollutant concentrations (CO, NO2, NOx), relative humidity, absolute humidity, and Temperature.
2. Model 2: Predicted AQI values over time using Pollutant concentrations (CO, NO2, NOx), the current month, and hour.
3. Model 3: Predicted AQI values over time using Pollutant concentrations (CO, NO2, NOx), relative humidity, absolute humidity, temperature, month, and hour.

## Models Compared 
Two supervised learning approaches were implemented:
1. K-Nearest Neighbors (KNN) - A non-parametric model that predicts concentration values by averaging nearby observations.
2. Random Forest (RF) - An ensemble machine learning method that handles non-linear relationships and interactions between features.

## Evaluation: 
Models were evaluated using the following metrics:
1. MSE (Mean Squared Error)
2. RMSE (Root Mean Squared Error)
3. MAE (Mean Absolute Error)
4. R^2

Each KNN regression model was trained using cross validation.

## Results:
It was observed that overall Model 2 performed the best. It had the lowest MSE, RMSE, and MAE which means it made the smallest average errors. Its R2 value of 0.98 means it was able to explain 98% of variance in target. Which indicated strong predictive power. This is further reinforced as Model 2 follows the line more closely and consistently with fewer outliers than the other two models.

Model 1 follows behind with the second best performance with slightly higher average errors than Model 2, but still a very accurate model. It also has the same R2 value of 0.98 which means it too has very strong predictive power. 

Model 3 performs the worst with the highest MSE, RMSE, and MAE which means that on average its predictions are further off than the other two models. It still has a very high R2 value of 0.97 so we can see that it has very good predictive power but is still clearly less accurate. 

Feaure Importance using Increase in MSE%:
1. NO2
2. NOx
3. CO
4. Hour
5. AH
6. Month
7. Temperature (T)
8. RH

The increase in MSE measures how much prediction error increases when a feature’s values are randomly shuffled. If permuting a feature results in poorer model performance then we conclude that that feature must be important. We can see now why Model 2 performs the best. Three of its five features are ranked as the most important with the remaining two separated only by one unused feature. For Model 1, we see that only two of its six features are ranked as most important with the remaining four ranked in the middle or as the least important. Finally we see that Model 3 having used all features, its poorer performance can be attributed to the noise produced by including unimportant features which can reduce the meaning of the distance between points, add elements of randomness to predictions, and allow for more important features to be overlooked. This is a potential issue that may arise when using a KNN model with this data set. 

Why a KNN regression model is appropriate:
AQI is influenced by local patterns in the pollutant levels and KNN regression makes predictions based on the values of nearby observations. Since these local patterns of pollutant levels directly influence the AQI it is reasonable for us to assume that similar pollutant levels will yield similar AQI values. 

## Limitations:
The models did not understand concepts like weekends, weekdays, seasonal changes, or cyclical patterns. Adding such features would allow the models to capture temporal patterns over time and would have increased model performance.  
