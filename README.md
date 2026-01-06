# Machine Learning Project
Sales Forecasting & Promotion Impact Analysis – Rossmann Retail
## Project Overview
Rossmann operates over 3000 drug stores in 7 European countries. Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied. This project focuses on forecasting daily retail sales and analyzing the impact of promotions, holidays, and seasonality on store performance using Python.The analysis includes data cleaning, exploratory data analysis (EDA), feature engineering, and regression-based modeling to predict sales and support business decisions related to pricing, promotions, and inventory planning. The project demonstrates an end-to-end data analytics workflow with a strong emphasis on business interpretation rather than just model performance.

## Business Problem
Retail businesses need accurate sales forecasts to optimize pricing, promotion planning, and inventory management. Incorrect forecasts can lead to stockouts, revenue loss, or excess inventory costs.

## Analytical Approach
Cleaned and validated historical sales and store-level data
Performed EDA to identify trends, seasonality, and promotion effects
Engineered features such as promotions, holidays, and store characteristics
Built and evaluated regression-based models for sales forecasting
Interpreted model results to derive business insights

## Key Insights
Promotions significantly increased daily sales across most stores
Sales showed strong weekly and seasonal patterns
Holiday periods had a noticeable impact on sales variability
Store type and competition distance influenced sales performance

## Dataset
- Source:Kaggle Dataset
  
- Training Data: Historical daily sales data for multiple Rossmann stores
   Features included: Store, Date, Sales, Promo, StateHoliday, SchoolHoliday, etc
- Store Data: Static information about stores, such as StoreType, Assortment, and CompetitionDistance
- Test Data: Similar structure as training data, without Sales column

## Feature Engineering
- Added flags: HasCompetition, HasPromo2

## Created dummy variables for categorical features
- StateHoliday, StoreType, Assortment

## Train/Test Alignment
- Ensured that test features matched training features for correct prediction.

## ML Models Used
- Linear Regression
- Random Forest Regressor
- XGBoost Regressor

## Evaluation Metrics
- RMSE (Root Mean Squared Error) — used to compare model performance

## Tools & Technologies
- Python (Pandas, NumPy, Matplotlib, Scikit-learn)
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Regression Analysis
- Model Evaluation

## Model Selection
- XGBoost performed best with validation RMSE ≈ 1152
- Further tuning improved performance to RMSE ≈ 1077 on validation

## Hyperparameter Tuning
- Used domain knowledge and iterative tuning (RandomizedSearchCV optional)
- Key XGBoost hyperparameters tuned: n_estimators, max_depth, learning_rate, subsample, colsample_bytree, min_child_weight

## Final Training
- Trained the final XGBoost model on the full training dataset (train + validation combined)
- Target variable was log-transformed (log1p) to stabilize variance
- Final RMSE on training data: ~971

## Test Predictions
- Preprocessed test dataset in the same way as training
- Ensured test columns matched training columns
- Predicted daily sales using the trained model
- Reversed log-transform using np.expm1
- Generated submission CSV with columns: Id and Sales

## Key Learnings
- Feature engineering is crucial — flags like HasCompetition and HasPromo2 improved predictions
- Tree-based models like XGBoost handle non-linear relationships and categorical features well
- Always ensure training and test features align exactly before prediction
- Log-transforming the target can help reduce the effect of outliers in sales

## Author
- S. Dhanya Das

