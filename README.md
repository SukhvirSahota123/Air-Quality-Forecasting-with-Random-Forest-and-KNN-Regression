# Air-Quality-Forecasting-with-Random-Forest-and-KNN-Regression
This project analyzes air quality data from the AirQualityUCI data set provided by the UCI Machine Learning Repository to predict pollutant concentrations and assess overall air quality levels using machine learning methods.

The data set includes hourly measurements of air pollutants (CO, NO2, O3), along with meteorological variable such as humidity and temperature collected from 2004-2005 in a small Italian city. Data preprocessing steps include removing missing values, correcting time/date formatting, and engineering features for analaysis.

Features used after preprocessing:
1. Temperature (°C)
2. Relative Humidity (%)
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


