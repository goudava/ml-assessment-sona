# ml-assessment-goudava

Machine Learning Fundamentals — Graded Assessment

## Structure

```
ml-assessment-goudava/
├── part_a/
│   ├── q1_supervised.ipynb          # Heart disease classification (28 marks)
│   ├── q2_unsupervised.ipynb        # Customer segmentation with K-Means + PCA (22 marks)
│   └── q3_feature_engineering.ipynb # Retail regression pipeline (20 marks)
├── part_b/
│   └── business_analysis.md         # Business case analysis (30 marks)
└── data/
    ├── q1_heart_disease.csv
    ├── q2_customers.csv
    └── q3_retail_promotions.csv
```

## Overview

### Part A: Python Coding (70 marks)

- **Q1 (28 marks):** Supervised learning — classification pipeline to predict heart disease using Decision Tree, Random Forest, and Gradient Boosting classifiers. Includes EDA, preprocessing, model evaluation, and GridSearchCV hyperparameter tuning.
- **Q2 (22 marks):** Unsupervised learning — K-Means customer segmentation using elbow method to select K, PCA for dimensionality reduction, and scatter plot visualisation coloured by cluster.
- **Q3 (20 marks):** Feature engineering and regression — scikit-learn pipeline with ColumnTransformer, temporal train-test split, Linear Regression vs Random Forest Regressor comparison, parity plots, and feature importance analysis.

### Part B: Business Case Analysis (30 marks)

Written analysis of a fashion retail chain's promotion effectiveness problem — covering ML problem formulation, EDA strategy, data joining approach, class imbalance handling, temporal evaluation design, feature importance communication, and end-to-end deployment with monitoring.

## Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
```

## How to Run

1. Place the CSV files in the `data/` folder (relative paths are used in all notebooks).
2. Open each notebook in JupyterLab or VS Code and run all cells.
3. All cells are pre-executed and outputs are saved.

## Marks Allocation and Rubric

### Part A — Python Coding (70 marks)

#### Q1 — Supervised Learning: Heart Disease Classification (28 marks)
- **Task 1 — Data Loading & Inspection (3 marks):** Load CSV, examine shape, dtypes, missing values. ✓
- **Task 2 — Exploratory Data Analysis (5 marks):** Target distribution, correlation heatmap, domain insights. ✓
- **Task 3 — Data Preprocessing (5 marks):** Imputation (median numerics, mode categoricals), one-hot encoding, standardisation. ✓
- **Task 4 — Model Training (5 marks):** Train Decision Tree, Random Forest, Gradient Boosting classifiers. ✓
- **Task 5 — Model Evaluation (6 marks):** Confusion matrices, classification reports (precision, recall, F1-score), comparison table. ✓
- **Task 6 — Hyperparameter Tuning (4 marks):** GridSearchCV on Gradient Boosting, document best params and CV results. ✓

**Results:**
- Best Model: Random Forest (Accuracy: 79.4%, F1: 0.794)
- Tuned Gradient Boosting: Accuracy: 76.9%, F1: 0.770
- Random Forest consistently outperforms due to variance reduction via bagging.

#### Q2 — Unsupervised Learning: Customer Segmentation (22 marks)
- **Task 1 — Data Loading & Inspection (3 marks):** Load customer data, describe features, check completeness. ✓
- **Task 2 — Exploratory Data Analysis (4 marks):** Feature distributions, correlation matrix, business context. ✓
- **Task 3 — Data Preprocessing (3 marks):** Imputation, StandardScaler (essential for K-Means distance-based algorithm). ✓
- **Task 4 — Choosing K with Elbow Method (4 marks):** Plot WCSS vs K, identify elbow at K=3, justify selection. ✓
- **Task 5 — K-Means Clustering (4 marks):** Fit K-Means with K=3, assign clusters, report cluster sizes and centroid profiles. ✓
- **Task 6 — PCA Visualisation (4 marks):** Apply PCA to 2D, colour-code clusters, show centroid positions, report explained variance. ✓
- **Task 7 — Cluster Interpretation (3 marks):** Describe business segments (low-value, mid-value, high-value customers). ✓

**Results:**
- Cluster 0 (Low-Value): 170 customers, £14.8k annual spend, 14 visits/month
- Cluster 1 (High-Value): 165 customers, £89.4k annual spend, 2.5 visits/month  
- Cluster 2 (Mid-Value): 165 customers, £43.3k annual spend, 8 visits/month
- PCA explains 89.2% of variance in first 2 components (PC1: 83.6%, PC2: 5.6%)

#### Q3 — Feature Engineering & Regression: Retail Promotions (20 marks)
- **Task 1 — Data Loading & Inspection (2 marks):** Load retail data, examine columns and summary statistics. ✓
- **Task 2 — Exploratory Data Analysis (3 marks):** Target distribution, promotion effectiveness by type, location impact. ✓
- **Task 3 — Feature Engineering (3 marks):** Temporal features (month, quarter), one-hot encode categoricals, final feature set. ✓
- **Task 4 — Train-Test Split with Temporal Grain (2 marks):** 60% train (months 1-3), 40% test (months 4-5), temporal ordering preserved. ✓
- **Task 5 — Model Training with scikit-learn Pipeline (4 marks):** Build pipelines with StandardScaler + LinearRegression and StandardScaler + RandomForestRegressor. ✓
- **Task 6 — Model Evaluation & Comparison (4 marks):** RMSE, MAE, R², parity plots, side-by-side comparison. ✓
- **Task 7 — Feature Importance Analysis (3 marks):** Extract RF feature importances, identify top drivers (location, festival, store size). ✓

**Results:**
- Linear Regression: Test RMSE 33.72, R²: 0.694
- Random Forest: Test RMSE 35.06, R²: 0.669
- Linear Regression performs better on this dataset (simpler feature relationships)
- Top 3 features: `location_type_urban` (21.9%), `is_festival` (18.3%), `store_size_small` (13.4%)

### Part B — Business Case Analysis (30 marks)

#### B1 — Problem Formulation (8 marks)
- **B1(a) — ML Problem Type (3 marks):** Supervised regression to predict `items_sold` as function of store/temporal/promotion features. ✓
- **B1(b) — Target Variable Justification (3 marks):** Why `items_sold` (not revenue): alignment with business goal, insensitivity to price/discount distortions. ✓
- **B1(c) — Global vs Location-Stratified Models (2 marks):** Rationale for location-specific models vs single global model. ✓

#### B2 — Data & EDA Strategy (10 marks)
- **B2(a) — Data Joining & Grain Definition (4 marks):** Join tables, define store × month grain, document aggregations. ✓
- **B2(b) — EDA Before Modelling (4 marks):** Four recommended analyses (promotion effectiveness, seasonality, correlations, location stratification). ✓
- **B2(c) — Class Imbalance Handling (2 marks):** Address 80% no-promotion skew via stratified sampling, weighting, or separate models. ✓

#### B3 — Model Evaluation & Deployment (12 marks)
- **B3(a) — Train-Test Split & Metrics (4 marks):** Temporal holdout strategy, RMSE/MAE/R²/ranking accuracy justification. ✓
- **B3(b) — Explaining Different Recommendations (4 marks):** How SHAP values explain promotion switches across months for same store. ✓
- **B3(c) — End-to-End Deployment Process (4 marks):** Model saving, inference pipeline, monitoring for drift/degradation, retraining triggers. ✓

---

## Submission Checklist

- [x] **Part A: Q1 Supervised Learning** — All 6 tasks with complete outputs and interpretation
- [x] **Part A: Q2 Unsupervised Learning** — All 7 tasks including K-Means, PCA, and cluster profiles
- [x] **Part A: Q3 Feature Engineering** — All 7 tasks including pipelines and feature importance
- [x] **Part B: Business Case Analysis** — All 30 marks covered (B1, B2, B3 sections)
- [x] **Data Files** — All three CSV files included in `data/` folder
- [x] **Reproducibility** — All notebooks pre-executed with outputs saved
- [x] **Documentation** — Clear task headings, interpretations, and results summaries

## Total Score: 100 marks (70 + 30)
