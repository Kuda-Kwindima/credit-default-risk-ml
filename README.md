# Credit Default Risk Modeling

## Goal
Predict probability of customer default to support risk-based lending decisions.

## Model
- XGBoost classifier
- Feature engineering (utilization & payment ratios)
- Cross-validation + RandomizedSearchCV
- SHAP explainability
- Probability calibration (isotonic)

## Results
- ROC AUC (Test): 0.782
- CV ROC AUC: 0.786
- Brier Score (original): 0.179
- Brier Score (calibrated): 0.134

## Key Drivers (SHAP)
Recent delinquency features (pay_0, pay_2) dominate, followed by utilization and credit limit.

![SHAP Summary](images/shap_summary.png)
![Calibration Curve](images/calibration_curve.png)

## Notes
This project includes threshold and calibration discussions for real-world banking use cases.
