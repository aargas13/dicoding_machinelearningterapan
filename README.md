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
#### Problem Statement:
Calorie expenditure is influenced by various factors such as age, gender, weight, activity type, and intensity. However, identifying which factors most strongly predict calorie burn remains a challenge. This limitation affects the ability to create accurate, individualized fitness and dietary plans.
#### Goals:
1. Identify the model that provides the best accuracy for predicting calorie expenditure
2. Determine the most relevant features to predict calorie expenditure
#### Solutions:

1. Simple Linear Regression: A basic regression approach that models the relationship between one predictor and calorie expenditure. Model accuracy can be measured with MAE or MSE
2. Random Forest Regression: A tree-based ensemble model that uses multiple decision trees to predict calorie expenditure. Model accuracy can be measured with MAE or MSE
3. XGBoost Regression: An advanced gradient boosting technique that iteratively improves predictions by minimizing errors. Model accuracy can be measured with MAE or MSE

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
- Workout_Type (e.g., Yoga, Cardio)
- Duration (e.g., hours per session)
- Max_BPM
- Avg_BPM
- Resting_BPM
- Workout_Frequency (days/week)	
  
Target Variable:
- Calories Burned: The output variable to be predicted.

#### Steps to Understand Data:
Basic Data Inspection:
- Use data.info() to check data types and null values.
- Use data.describe() to summarize numerical variables.
  
Univariate Analysis:
- Barplots
- Distribution Plot
  
Multivariate Analysis:
- Heatmap
Outlier Detection:
- Boxplot

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
##### Advantage:
Simplicity: Easy to implement and interpret.
##### Disadvantage:
Assumes Linearity: Cannot capture complex, non-linear relationships.

#### Random Forest Regression:
##### Advantage:
Handles Non-Linearity: Can model complex relationships
Robust to Outliers: Less sensitive to extreme values due to averaging.
##### Disadvantage:
Black Box Nature: Less interpretable than linear regression.

#### XGBoost Regression:
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
