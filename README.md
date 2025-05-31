# Real-Estate-Price-Prediction

This project applies econometric modeling techniques to a real estate dataset to analyze and predict housing prices. The workflow involves data cleaning, exploratory analysis, linear regression, multicollinearity checks, best subsets regression, and model diagnostics.

**Dataset**

File: real_estate_data.csv

Features include:

Square_Feet, Num_Bedrooms, Num_Bathrooms, Num_Floors, Year_Built

Has_Garden, Has_Pool

Price (target variable)

**Objectives**

Clean and preprocess the dataset

Explore and visualize variable relationships

Fit linear regression models

Evaluate model performance and assumptions

Perform multicollinearity checks using VIF

Identify optimal predictor sets using Best Subset Regression

**Technologies Used**

Python (Pandas, NumPy, Matplotlib, Seaborn)

scikit-learn

statsmodels

**Workflow Summary**

*1. Data Cleaning & Preprocessing*

Removed duplicates and handled outliers (IQR method)

Visualized and reported missing values

Saved a cleaned dataset (cleaned_data.csv)

*2. Exploratory Data Analysis*

Scatter plots and correlation analysis with Price

Created a heatmap to understand variable relationships

Found moderate correlations for Square_Feet, Num_Bedrooms, etc.

*3. Initial Linear Regression Model*

Used LinearRegression from scikit-learn

Achieved:

MAE ≈ 22,919

R² ≈ 0.94

Model explains 94% of price variance

*4. Multicollinearity Check*

Used VIF (Variance Inflation Factor)

All predictors had VIF < 5 (no multicollinearity)

*5. Best Subset Regression*

Evaluated all combinations of predictors

Selected model based on:

Minimum Mallows’ Cp

Maximum Adjusted R²

Lowest Standard Error

*Best Model:*

Predictors: Square_Feet, Num_Bedrooms, Num_Bathrooms, Num_Floors, Year_Built, Has_Garden, Has_Pool

Adjusted R²: 0.9438

Standard Error: 10,161.72

**Model Interpretation**

Variable	Effect on Price (approx.)

Square_Feet	+$987.89 per additional sq ft

Num_Bedrooms	+$49,740 per bedroom

Num_Bathrooms	+$31,430 per bathroom

Num_Floors	+$19,700 per floor

Year_Built	+$1,516 per newer year

Has_Garden	+$28,800 if garden present

Has_Pool	+$42,650 if pool present

**Model Diagnostics**

Residuals vs Fitted Plot: No visible pattern (linearity assumption holds)

Q-Q Plot: Residuals are approximately normally distributed

Durbin-Watson: 2.07 → no serious autocorrelation

Goldfeld-Quandt Test:

p-value > 0.05 → Homoscedasticity holds

**Conclusions**

The final model is statistically strong, interpretable, and satisfies linear regression assumptions.

It explains ~94% of the variance in housing prices with no signs of multicollinearity or heteroscedasticity.

**Outputs**

Cleaned dataset: cleaned_data.csv

Console logs include model summaries, metrics, and subset analysis
