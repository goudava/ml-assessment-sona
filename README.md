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
