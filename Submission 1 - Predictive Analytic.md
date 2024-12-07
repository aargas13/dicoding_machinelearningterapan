# Laporan Proyek Machine Learning - Albertus Arga S
## Title: Calorie Expenditure Prediction Using Regression Methods
### Purpose of Research:
This research contributes by deepening our understanding of how demographic and physiological factors such as age, gender, weight, and activity type and duration impact calorie expenditure. Healthcare professionals and gym trainers, and even the general public can use calorie predictions to find the most fitting exercises routines.

#### Supporting Research:
[1]
A. Kadam, A. Shrivastava, S. K. Pawar, V. H. Patil, J. Michaelson, and A. Singh, “Calories Burned Prediction Using Machine Learning,” vol. 12, pp. 1712–1717, Sep. 2023, doi: https://doi.org/10.1109/ic3i59117.2023.10397623.

‌[2]
Marte Nipas, A. G. Acoba, J. N. Mindoro, Mon, J. Ann, and J. S. Gulmatico, “Burned Calories Prediction using Supervised Machine Learning: Regression Algorithm,” 2022 Second International Conference on Power, Control and Computing Technologies (ICPC2T), Mar. 2022, doi: https://doi.org/10.1109/icpc2t53885.2022.9776710.
‌
### Business Understanding:
#### Background:
Calorie expenditure is a critical aspect of understanding human metabolism and designing effective health interventions. It is influenced by various factors, including age, gender, weight, height, activity type, duration, and intensity. These factors collectively determine the rate at which the body burns calories, both at rest and during physical activity. However, due to the complex interplay of these factors, accurately predicting calorie expenditure for individuals remains challenging. Machine learning can be a tool to predict calorie expenditure and determining the most relevant factors.

#### Problem Statements:
1. What is the best model to predict calorie expenditure?
2. There are many factors that affect calorie expenditure, what factor is the most relevant?
3. Does different exercises greatly affect how much calories are burned?
    
#### Goals:
1. Identify the model that provides the best accuracy for predicting calorie expenditure
2. Determine the most relevant features to predict calorie expenditure
3. Determine whether or not different exercises affect calorie expenditure greatly
   
#### Solutions:

1. Simple Linear Regression: A basic regression approach that models the relationship between one predictor and calorie expenditure. Model accuracy can be measured with MAE or MSE
2. Random Forest Regression: A tree-based ensemble model that uses multiple decision trees to predict calorie expenditure. Model accuracy can be measured with MAE or MSE. It also determines the most relevant features.
3. XGBoost Regression: An advanced gradient boosting technique that iteratively improves predictions by minimizing errors. Model accuracy can be measured with MAE or MSE. It also determines the most relevant features.

#### Impact:
Contribution to Science:
Identifying the most influential factors in calorie expenditure contributes to sports science and human physiology, providing deeper insights into metabolic functions and energy dynamics.


### Data Understanding:
#### Dataset Description:
The Gym Members Exercise Dataset contains information related to gym members' characteristics, their exercises, and associated calorie expenditure. The key components of understanding the dataset involve assessing its features and their potential influence on calorie burn predictions.
#### Features:
Member Characteristics:
- Age
- Gender
- Weight (kg)
- Height (m)
- Fat_Percentage
- Water_Intake (liters)
- Experience_Level
- BMI
  
Exercise Details:
- Workout_Type 
- Session_Duration (hours)
- Max_BPM
- Avg_BPM
- Resting_BPM
- Workout_Frequency (days/week)	
  
Target Variable:
- Calories_Burned: The output variable to be predicted.

#### Steps to Understand Data:
Basic Data Inspection:
- Use data.info() to check data types and null values.
- Use data.describe() to summarize numerical variables.
  
Univariate Analysis:
- Countplot
  Example:<br>
  ![Countplot](countplot.png)
  
- Distribution Plot
  Example:<br>
  ![Countplot](displot.png)
  
Multivariate Analysis:
- Heatmap
  Example:<br>
  ![Heatmap](heatmap.png)
- Barplot
  Example:<br>
  ![Barplot](barplot.png)
  
Outlier Detection:
- Boxplot
- Example:<br>
  ![Boxplot](boxplot.png)


### Data Preparation:
#### Removing Outliers:
Why Needed: Outliers can skew model predictions.

#### Binning Continuous Variables:
Why Needed: Simplifies the analysis of continuous variables (e.g., age).

#### Scaling:
Why Needed: Features may have different units and ranges, affecting model performance.

#### Encoding Categorical Variables:
Why Needed: Machine learning models like XGBoost require numeric inputs.

#### Splitting Data:
Why Needed: Prevents data leakage


### Modeling:
#### Simple Linear Regression:
##### How it works:
Models the relationship between one independent variable and a dependent variable by fitting a straight line.
##### Advantage:
Simplicity: Easy to implement and interpret.
##### Disadvantage:
Assumes Linearity: Cannot capture complex, non-linear relationships.

#### Random Forest Regression:
##### How it works:
An ensemble method that uses multiple decision trees on random subsets of data and averages their predictions. Parameters used are n_estimators = 100, random_state = 42.
##### Advantage:
Handles Non-Linearity: Can model complex relationships
Robust to Outliers: Less sensitive to extreme values due to averaging.
##### Disadvantage:
Black Box Nature: Less interpretable than linear regression.

#### XGBoost Regression:
##### How it works:
A gradient boosting algorithm that builds decision trees iteratively, correcting errors from previous iterations. Parameters used are n_estimators = 100, learning_rate = 0.1, max_depth = 3, random_state = 42.
##### Advantage:
High Performance: Often achieves state-of-the-art accuracy for structured/tabular data.
##### Disadvantage:
Computationally Intensive: Training can be slow for very large datasets.


### Evaluation:
#### Mean Squared Error:
MSE is a metric used to measure the average squared difference between the actual and predicted values in regression models.
![MSE](mse.png)
#### Feature Importance:
Feature importance quantifies the contribution of each input feature to the predictive power of a machine learning model. It helps in understanding the relative importance of predictors and their impact on the target variable.
#### R²:
R² is a statistical measure that indicates how well a regression model explains the variability of the target variable  based on the predictor variables. It is commonly used to evaluate the goodness of fit for regression models.
![R2](r2.png)


### Insights
1. From the Scatterplot, we can see that calories burned are highly correlated with Session_Duration(hours)

2. From Barplots, there are no big difference in calories burned between types of exercises

3. From the simple linear model, Session_Duration(hours) captures most of the variability in the data (82%), but it has a high value of MSE of 11849 and  12834.

5. From the RF Regressor,  Session_Duration(hours) is the most relevant feature with a value of 0.82. The model captures 98% of variability, but the training MSE (279) is way lower than the test MSE (1343), which could indicate that the model overfitted. 
    
6. From the XGB Regression, Session_Duration(hours) is the most relevant feature with a F-Score value of 261. The model captures 99% of variability. The training MSE is quite low (150), with not too big of a difference compared to test MSE (328).

Therefore, XGB Regressor is the best model to predict calorie expenditure.

This also means that the type of exercise isn't the most important factor to burn calories, but how long people exercise for.


### Conclusion
1. **What is the best model to predict calorie expenditure?**

   XGB Regressor is the best model to predict calorie expenditure.
   
2. **There are many factors that affect calorie expenditure, what factor is the most relevant?**

   Session_Duration(hours) is the most relevant feature.

3. **Does different exercises greatly affect how much calories are burned?**

   No, what matters the most is the duration of the session.

   
### Impact
This research contributed to science by identifying the most relevant factor that determines the amount of calorie spent by exercising.
