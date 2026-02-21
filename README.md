# Credit Default Risk Modeling (Finance + ML + Business)

## 🎯 Objective
Build a calibrated probability model to predict credit default risk and support risk-based financial decision-making.

---

## 💼 Business Context

In lending, model errors have financial consequences:

- False Negative (missed defaulter) → direct financial loss  
- False Positive (flag good customer) → lost revenue + customer friction  

This project frames ML as a **business decision tool**, not just a classifier.

---

## 🧠 Modeling Approach

- Data cleaning & type validation
- Feature engineering (utilization & payment ratios)
- XGBoost classifier
- Cross-validation + hyperparameter tuning
- Threshold optimization
- SHAP explainability
- Probability calibration (Isotonic regression)

---

## 📊 Performance

- ROC AUC (Test): ~0.78  
- Cross-Validation ROC AUC: ~0.786  
- Original Brier Score: 0.179  
- Calibrated Brier Score: 0.134 ✅  

Calibration improved probability reliability significantly.

---

## 🔍 Key Insights (SHAP)

- Recent delinquency (PAY_0, PAY_2) is strongest risk driver  
- Higher credit limits reduce predicted default probability  
- Utilization ratios add additional predictive power  

---

## ⚠️ Governance & Real-World Considerations

- Monitor for economic regime changes  
- Perform periodic recalibration  
- Review fairness and compliance  
- Address reject inference limitations  

---

## 🛠 Tech Stack

Python, Pandas, Scikit-learn, XGBoost, SHAP, Matplotlib
