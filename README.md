# Employee Retention Prediction

## Project Overview
This project aims to predict employee retention using machine learning models. The analysis identifies patterns and factors that influence employee departure, helping organizations understand and reduce turnover.

## Dataset
- **Source**: HR_comma_sep.csv
- **Target Variable**: `left` (1 = employee left, 0 = employee stayed)
- **Size**: 14,999 employees × multiple features

## Features
The dataset includes the following features:
- **satisfaction_level**: Job satisfaction rating
- **time_spend_company**: Years spent at the company
- **average_montly_hours**: Average monthly working hours
- **promotion_last_5years**: Number of promotions in the last 5 years
- **Department**: Employee's department
- **salary**: Salary level (low, medium, high)
- **last_evaluation**: Performance evaluation score
- **number_project**: Number of projects the employee worked on
- **Work_accident**: Whether the employee had a workplace accident (binary)
- **left**: Target variable - whether the employee left (1) or stayed (0)

## Data Processing
1. **Duplicate Removal**: Removed 3,008 duplicate records
2. **Feature Removal**: Dropped `last_evaluation` and `number_project` columns
3. **Encoding**: Applied one-hot encoding for categorical variables:
   - Salary levels (high, low, medium)
   - Departments (IT, R&D, accounting, HR, management, marketing, product management, sales, support, technical)

## Models & Results

### Random Forest Classifier
- **Best Parameters**:
  - n_estimators: 100
  - max_depth: 20
  - min_samples_leaf: 2
  - min_samples_split: 10
  - max_features: log2
- **Accuracy**: High accuracy on the test set
- **Visualization**: Confusion matrix displayed for performance analysis

### XGBoost Classifier
- **Best Parameters**:
  - n_estimators: 100
  - learning_rate: 0.05
  - max_depth: 7
- **Accuracy**: Competitive performance with Random Forest
- **Advantages**: Efficient training and potentially better generalization

## Key Insights
- Exploratory Data Analysis (EDA) performed with histograms and correlation heatmap
- Correlation analysis reveals relationships between features and employee retention
- Both models provide actionable insights for HR decision-making

## Libraries Used
- **Data Processing**: NumPy, Pandas
- **Visualization**: Matplotlib, Seaborn
- **Machine Learning**: Scikit-learn, XGBoost

## Model Evaluation
- **Train-Test Split**: 70% training, 30% testing
- **Scaling**: StandardScaler applied for feature normalization
- **Metrics**: Accuracy, Confusion Matrix, Classification Report

## How to Run
1. Ensure all dependencies are installed
2. Load the HR dataset
3. Execute cells sequentially to:
   - Load and explore data
   - Preprocess and encode features
   - Train Random Forest and XGBoost models
   - Evaluate model performance

## Future Improvements
- Implement additional algorithms (Gradient Boosting, Neural Networks)
- Feature engineering for better predictive power
- Cross-validation strategies
- Hyperparameter tuning optimization
- Business-oriented recommendations based on model insights
