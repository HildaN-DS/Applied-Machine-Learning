# Data Preprocessing and Leakage-Safe Features

## Course

**DSA 8401 – Applied Machine Learning**  
**Programme:** Master in Data Science and Analytics

## Assignment Overview

This assignment focuses on preparing messy transactional data for machine learning while preventing data leakage.

The analysis uses a synthetic mobile-money transaction dataset and covers data quality assessment, missing-data analysis, entity resolution, feature engineering, leakage detection, and the construction of a reproducible Scikit-learn modelling pipeline.

The main objective is to demonstrate that good model performance is only meaningful when preprocessing, feature construction, and validation are performed without leaking information from the future or across related observations.

## Dataset

The analysis uses:

```text
data/mobile_money_statements.csv
```

## Requirements

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

## Structure

01-Data-Preprocessing-and-Leakage/
│
├── README.md
│
├── data/
│   ├── mobile_money_statements.csv
│   
│
├── models/
│   ├── 053837_credit_risk_pipeline.joblib
│   └── 053837_credit_risk_pipeline_meta.json
│
├── notebook/
│   └── data_pre-processing.ipynb
│
└── reports/