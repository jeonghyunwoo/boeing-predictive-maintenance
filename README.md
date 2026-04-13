# Aircraft Engine Remaining Useful Life Prediction using NASA CMAPSS

## Overview

This project demonstrates a predictive maintenance workflow for aircraft engines by estimating **Remaining Useful Life (RUL)** using the NASA **CMAPSS turbofan engine degradation dataset**.

The focus is not only on model accuracy, but on building a pipeline that supports **practical maintenance decision-making**.

---

## Key Results

- Best Validation RMSE: **12.67**
- Test RMSE: **15.59 (raw)** / **14.31 (capped)**
- Error characteristics vary across lifecycle stages and operating conditions
- Setting-aware modeling helps reduce variance differences across regimes

---

## Problem Context

Aircraft engines generate high-frequency sensor data during operation.

Estimating RUL enables:

- early identification of degradation
- proactive maintenance scheduling
- prioritization of high-risk engines
- reduction of unexpected downtime

---

## Approach

### 1. Feature Engineering

To capture degradation dynamics:

- rolling mean / std (multi-window)
- exponentially weighted moving average (EWMA)
- first differences
- cumulative statistics

These features summarize both **sensor behavior** and **temporal degradation patterns**.

---

### 2. Data Leakage Prevention

- Removed features such as `cycle_ratio` that depend on full lifecycle information
- Ensured all features are available at prediction time

---

### 3. RUL Capping

- Applied **RUL cap = 125**
- Prevents the model from overfitting early healthy cycles

---

### 4. Modeling Strategy

- Baseline: RandomForest
- Extended models: Gradient Boosting family
- Setting-aware modeling using clustering on operational conditions

This allows the model to account for **different operating regimes**.

---

## Key Observations

### Heteroscedasticity

- Prediction variance increases when engines are in early lifecycle (high RUL)
- Errors become more stable near end-of-life

### Operating Conditions

- Sensor distributions vary depending on operational settings
- Segmenting data by settings improves consistency of predictions

---

## Actionable Insights

### 1. Condition-Based Maintenance (CBM)

- Use model outputs to prioritize engines with low predicted RUL
- Supports dynamic maintenance scheduling instead of fixed intervals

---

### 2. Risk-Based Inspection Prioritization

- For high-risk engines, model explanations (e.g., SHAP) can highlight contributing sensors
- Helps narrow inspection scope and reduce diagnostic time

---

### 3. Avoid Over-Maintenance

- Early-stage engines (high RUL) show natural prediction variability
- Minor fluctuations should not trigger unnecessary maintenance

---

## Full Report

See the complete analysis:

- `reports/predictive_maintenance_rul_model.html`

---

## Repository Structure

```text
.
├── predictive_maintenance_rul_model.ipynb   # main analysis notebook
├── reports/
│   ├── predictive_maintenance_rul_model.html   # final report
├── outputs/
│   └── figures/                             # generated plots
└── README.md
```

---

## How to Use

Open the notebook:

```text
predictive_maintenance_rul_model.ipynb
```

View the final report:

```text
reports/predictive_maintenance_report.html
```

---

## Technologies

- Python
- pandas / NumPy
- scikit-learn
- LightGBM / XGBoost
- matplotlib / seaborn
- SHAP
- Quarto

---

## Notes

This project is based on the NASA CMAPSS simulation dataset and is intended as an illustrative example of predictive maintenance modeling.

---

## Author

Hyunwoo Jeong  
GitHub: https://github.com/jeonghyunwoo
