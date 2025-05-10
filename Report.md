**Energy Consumption Prediction Using Machine Learning**

**Introduction**:

This project focuses on predicting equipment energy consumption based on various environmental and indoor conditions such as temperature, humidity, pressure, and lighting. The dataset contains readings from multiple zones within a building and includes weather data like wind speed and visibility.

The main goal is to use machine learning to understand which factors affect energy usage the most and then build a model that can predict energy consumption.

**Dataset Description**:

The dataset contains the following:

1.timestamp: Date and time of the reading.

2.equipment_energy_consumption: The target variable we want to predict.

3.zone temperature & humidity: From zone1 to zone9.

4.outdoor_temperature, atmospheric_pressure, outdoor_humidity

5.wind_speed, visibility_index, dew_point

6.random_variable1, random_variable2: Additional values.

**Data Preprocessing**:
1.Handled missing values using fillna() with the forward fill method.

2.Converted timestamps into datetime format (though it wasn’t used in modeling).

3.Selected only the numerical columns for correlation and modeling.

4.Removed the timestamp column before training.

**Exploratory Data Analysis (EDA)**:
1.Used correlation heatmap to understand relationships between features.

2.Found that temperature and humidity in several zones show correlation with energy usage.

3.Outliers were visible in some plots, but not removed for this version.

**Model Building**:

1.Chose Random Forest Regressor for training as it handles non-linearity and works well for tabular data.

2.Performed train-test split (80-20).

3.Evaluated using R² Score and RMSE.

4.Cross-validation (cv=5) was also performed to get more robust performance.

**Model Results**:

1.R² Score on Test Set: ~0.88 (can vary slightly run to run)

2.Root Mean Squared Error (RMSE): ~27.16

The model predicts energy consumption quite well.

**Feature Importance**:

Important features based on Random Forest:

1.zone1_temperature

2.zone3_humidity

3.lighting_energy

4.outdoor_temperature

5.wind_speed

These factors were found to influence energy usage the most.

**Predicted vs Actual Plot**:

A scatter plot was generated between actual and predicted energy usage values. The red line represents perfect predictions. Most points were close to this line, which shows the model performs reasonably well.

**Conclusion**:

This project showed how machine learning, particularly Random Forest, can be applied to predict energy consumption in smart buildings using sensor data. Further improvements can be made by tuning hyperparameters or trying advanced models like Gradient Boosting or XGBoost.

**Future Work**:

1.Tune hyperparameters using GridSearchCV.

2.Add time-based features from the timestamp (hour, day, etc.).

3.Try ensemble methods like XGBoost or LightGBM for improved accuracy.

4.Build a real-time dashboard for predictions.

