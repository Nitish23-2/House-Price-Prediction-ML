# House Price Prediction using Machine Learning

## Overview
This project focuses on predicting housing prices using structured real estate data. The objective is to build a robust regression pipeline that can accurately estimate property prices based on location, size, amenities, and other relevant features.

The project involves end-to-end machine learning workflow including data preprocessing, feature engineering, outlier handling, model training, and evaluation using multiple regression techniques.

---

## Dataset
- Training and test datasets containing real estate features :contentReference[oaicite:0]{index=0}  

### Key Features
- Property attributes: total_sqft, size (BHK), bath, balcony  
- Location-based features: location, area_type  
- Availability status  
- Target variable: price  

---

## Methodology

### Data Preprocessing
- Converted complex formats (e.g., range values in total_sqft) into numerical values  
- Extracted numerical values from categorical size feature  
- Handled missing values using:
  - Median imputation for numerical features  
  - Mode imputation for categorical features  
- Ensured no data leakage by using training statistics for test data  

---

### Outlier Handling
- Removed unrealistic entries based on domain logic:
  - Bathroom count constraints relative to BHK  
  - Minimum square footage per room  
- Applied price-per-square-foot normalization:
  - Grouped by location  
  - Capped extreme values using standard deviation  
- Recomputed price after normalization  

---

### Feature Engineering
- Encoded availability as binary feature  
- Reduced dimensionality of location:
  - Grouped rare categories into "other"  
- Applied One-Hot Encoding for categorical variables  
- Scaled numerical features using StandardScaler  

---

### Data Preparation
- Combined train and test data to ensure consistent encoding  
- Performed train-validation split (80-20) for model evaluation  

---

## Models Implemented

### Baseline Models
- Linear Regression  
- Lasso Regression  

### Ensemble Models
- Random Forest Regressor  
- Gradient Boosting Regressor  
- AdaBoost Regressor  

### Advanced Models
- XGBoost  
- LightGBM  
- CatBoost  

---

## Model Evaluation

- Evaluation metrics:
  - R² Score  
  - Root Mean Squared Error (RMSE)  

- Gradient Boosting and CatBoost showed strong performance  
- Final model selected based on validation performance  

---

## Key Results
- Achieved strong predictive performance with ensemble models  
- Boosting algorithms significantly outperformed linear models  
- Feature engineering and outlier handling improved model stability  

---

## Feature Importance
- Performed feature importance analysis using CatBoost  
- Identified key drivers of price:
  - Location  
  - Total square footage  
  - Number of rooms (BHK)  
  - Amenities (bath, balcony)  

---

## Key Insights
- Location plays a dominant role in price prediction  
- Feature engineering has a significant impact on model performance  
- Proper handling of outliers improves generalization  
- Ensemble methods are more effective for structured regression problems  

---

## Tech Stack
- Python  
- Pandas, NumPy  
- Scikit-learn  
- XGBoost, LightGBM, CatBoost  
- Matplotlib, Seaborn  

---

## Future Improvements
- Hyperparameter tuning using GridSearch / Bayesian optimization  
- Incorporating geospatial features  
- Deploying model as an API  
- Using advanced feature selection techniques  

---

## Author
Nitish Bhatt  
BS Data Science and Applications (IIT Madras) + B.Tech Mechanical Engineering (GBPUAT)
