# Credit Default Risk Modeling (Finance + ML + Business)

## Goal
Build a **calibrated probability model** to predict credit default risk and support risk-based decision-making (approval, review, pricing, and capital allocation).

## Business framing
In lending, mistakes have different costs:

- **False Negative (miss a defaulter)** → potential loan loss
- **False Positive (flag a good customer)** → lost revenue + customer friction

This project treats the model as a **decision tool**, not only a classifier.

## Dataset
UCI Credit Card Default Dataset (Taiwan).  
Source: https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients

> Raw data is not included in the repo. See `data_raw/README.md`.

## Approach
- Data cleaning + type validation (no object dtypes)
- Feature engineering (utilization ratios, payment ratios)
- Model: **XGBoost (XGBClassifier)**
- Cross-validation + hyperparameter tuning
- Threshold tuning (precision/recall trade-off)
- Error analysis (FP/FN drivers)
- Explainability: **SHAP**
- Probability calibration: **Isotonic calibration** (reliability improvement)

## Results (Test Set)
- **ROC AUC:** ~0.78  
- **CV ROC AUC:** ~0.786  
- **Brier Score (original):** 0.179  
- **Brier Score (calibrated):** 0.134  ✅ (probabilities became more reliable)

## Key drivers (Explainability)
SHAP analysis showed that repayment status features dominated risk prediction:
- `pay_0`, `pay_2`, `pay_3` are strong risk signals (recent delinquency)
- Higher `limit_bal` generally reduces predicted risk
- Utilization ratios add additional signal

## Model risk & real-world considerations
If deployed in a bank, the model should include:
- **Monitoring for drift** (portfolio composition and economic regime changes)
- **Periodic recalibration** to keep probabilities reliable
- **Fairness review** and policy constraints
- Documentation for governance (assumptions, limitations, validation)

## Repository structure
- `notebooks/` – analysis and modeling notebooks
- `data_raw/` – dataset reference (no raw data included)

## Next steps
This project is part of a larger portfolio focused on **business ML impact**.
Next: **Retail Revenue Optimization** (profit-driven modeling).
