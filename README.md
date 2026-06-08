# Cirrhosis Prediction Project

## 📊 Project Overview
This project aims to predict cirrhosis (liver disease) progression using patient clinical data. The model classifies patients into different stages/statuses of cirrhosis based on various medical measurements.

## 🎯 Objective
Develop a robust machine learning model to predict cirrhosis status using clinical features such as:
- Bilirubin levels
- Cholesterol
- Albumin
- Copper
- Alkaline Phosphatase
- SGOT
- Triglycerides
- Platelets
- Prothrombin time
- And more (age, sex, drug treatment, etc.)

## 📁 Dataset
- **Training data**: 7,905 patients with 20 features
- **Test data**: Separate holdout set
- **Target variable**: Status (C/CL/D - indicating cirrhosis progression)

## 🔍 Methodology

### 1. Exploratory Data Analysis (EDA)
- Statistical summaries using `skimpy`
- Correlation analysis (Spearman correlation heatmap)
- Target variable distribution visualization
- Data quality assessment

### 2. Preprocessing
- Feature encoding for categorical variables (Drug, Sex, Ascites, Hepatomegaly, Spiders, Edema)
- Feature scaling/normalization
- Handling class imbalance using:
  - **SMOTE** (Synthetic Minority Over-sampling Technique)
  - **ADASYN** (Adaptive Synthetic Sampling)

### 3. Feature Engineering & Selection
- **PCA** (Principal Component Analysis) for dimensionality reduction
- **LDA** (Linear Discriminant Analysis) for feature transformation
- **SelectKBest** with mutual information for feature selection

### 4. Modeling Approach
Multiple algorithms implemented and evaluated:

**Single Models:**
- Logistic Regression (with cross-validation)
- Ridge Classifier
- Radius Neighbors Classifier
- Random Forest Classifier
- XGBoost Classifier
- LightGBM Classifier
- CatBoost Classifier

**Ensemble Methods:**
- **Stacking Classifier** - Combines multiple base models
- **Voting Classifier** - Ensemble voting mechanism

### 5. Experiment Tracking
- **MLflow integration** for experiment logging and model versioning
- Tracks parameters, metrics, and model artifacts

## 📈 Evaluation Metrics
- Accuracy
- Classification report (precision, recall, F1-score)
- Cross-validation scores

## 🏆 Results & Key Findings

### Standout Features of this Project:

1. **Comprehensive Model Comparison** - Tests 8+ algorithms from traditional logistic regression to advanced gradient boosting (XGBoost, LightGBM, CatBoost)

2. **Sophisticated Ensemble Methods** - Implements stacking and voting classifiers for improved predictive performance

3. **Multiple Resampling Techniques** - Addresses class imbalance using both SMOTE and ADASYN

4. **Feature Reduction Techniques** - Applies PCA and LDA alongside feature selection methods

5. **MLflow Integration** - Professional experiment tracking for reproducibility

6. **Statistical Rigor** - Performs Kruskal-Wallis tests and thorough correlation analysis

7. **Class Imbalance Handling** - Recognizes and properly addresses imbalanced medical dataset

## 💻 Technologies Used

```python
# Core Libraries
- pandas, numpy for data manipulation
- matplotlib, seaborn for visualization

# Machine Learning
- scikit-learn (preprocessing, model selection, metrics)
- xgboost, lightgbm, catboost
- imblearn (SMOTE, ADASYN, Pipeline)

# Experiment Tracking
- mlflow
- joblib for model persistence
```

## 🚀 How to Run

1. **Install dependencies:**
```bash
pip install imblearn skimpy mlflow xgboost lightgbm catboost
```

2. **Mount data directory** (if using Google Colab):
```python
from google.colab import drive
drive.mount('/content/drive')
```

3. **Load and preprocess data** as shown in the notebook

4. **Train models** and track experiments with MLflow

## 📊 Key Visualizations
- Correlation heatmap showing feature relationships
- Target variable distribution plot
- Feature distributions using skimpy summaries

