# 02-ML-Pipelines-and-Modeling


## Overview

This folder contains the complete Assignment 2 workflow for cost-sensitive
fraud classification using the unchanged output of Assignment 1.

The workflow covers:

- strict out-of-time holdout evaluation;
- five-fold blocked/purged temporal cross-validation;
- regularised Logistic Regression, Random Forest and LightGBM;
- class weighting and SMOTE-NC imbalance experiments;
- a deliberate pre-CV resampling anti-pattern demonstration;
- 60-trial Optuna hyperparameter tuning;
- probability calibration using Platt/isotonic comparison;
- cost-sensitive threshold selection;
- global and local SHAP explanations;
- subgroup fairness analysis by region and segment;
- final untouched holdout evaluation.

## Structure

```text
02-ML-Pipelines-and-Modeling/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── 053837_assignment2.ipynb
├── data/
│   └── 053837_a1_modelling_table.pkl
├── models/
│   └── 053837_credit_risk_pipeline_meta.json
├── figures/
│   ├── final_pr_curves.png
│   ├── reliability_diagram.png
│   ├── a2_optuna_history.png
│   ├── shap_global_summary.png
│   └── shap_waterfall.png
├── db/
│   └── 053837_a2_optuna_study.db
├── a2_data/
│   ├── model_comparison.csv
│   ├── base_model_fold_results.csv
│   ├── imbalance_comparison.csv
│   ├── calibration_comparison.csv
│   ├── development_cost_threshold_comparison.csv
│   ├── fairness_by_region.csv
│   ├── fairness_by_segment.csv
│   ├── purged_cv_fold_summary.csv
│   ├── development_oof_predictions.csv
│   ├── final_holdout_predictions.csv
│   ├── final_holdout_metrics.csv
│   └── final_holdout_cost_comparison.csv
├── a2_models/
│   ├── final_model.joblib
│   └── calibration_and_threshold.joblib
└── report/
    ├── 053837_A2_Cost_of_Being_Wrong_Report.pdf
    
```

## Reproducing the results

1. Clone the repository.
2. Create and activate a Python virtual environment.
3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Confirm that the Assignment 1 artefacts exist at:

```text
data/053837_a1_modelling_table.pkl
models/053837_credit_risk_pipeline_meta.json
```

5. Start Jupyter from the repository root:

```bash
jupyter notebook
```

6. Open:

```text
notebooks/053837_assignment2.ipynb
```

7. Run all cells from top to bottom.

The notebook uses `PROJECT_ROOT = Path("..")`, so it should be executed from the
`notebooks/` folder inside this repository structure.

## Final decision

The final selected model is tuned LightGBM with Platt calibration and a fixed
cost-sensitive fraud-flag threshold of **0.0784**.

The threshold was selected on development data only and was evaluated once on
the untouched out-of-time holdout.

## Important evaluation rule

The final holdout must not be used for:

- model selection;
- hyperparameter tuning;
- calibration selection;
- threshold optimisation;
- feature selection.

It is opened only after all modelling decisions have been frozen.
