# Boeing Predictive Maintenance Portfolio
**Remaining Useful Life (RUL) Prediction and Maintenance Brief Generation using NASA CMAPSS**

## Overview
This project is a predictive maintenance portfolio built for the Boeing Data Scientist application.  
Using the NASA CMAPSS turbofan engine degradation dataset, it predicts Remaining Useful Life (RUL) from multivariate time-series sensor data and generates an action-oriented maintenance brief for a selected engine.

The goal of this project is not only to build an accurate regression model, but also to demonstrate a practical data science workflow aligned with real-world industrial use cases:
- time-series and tabular data analysis
- feature engineering from complex sensor signals
- model evaluation and validation
- operational interpretation of predictions
- structured reporting for decision support

## Why This Project Fits Boeing
The Boeing Data Scientist role emphasizes:
- large-scale time-series and tabular data analysis
- predictive modeling and forecasting
- experimentation and model validation
- robust data pipelines and automated workflows
- clear communication of findings through reports and visualizations
- well-organized Git repositories

This repository is designed to reflect those requirements through an end-to-end prototype:
1. preprocessing raw sensor data
2. engineering rolling-window features
3. training and evaluating an RUL prediction model
4. visualizing model outputs
5. generating a maintenance-oriented summary from prediction results

## My Perspective
My professional background has centered on predictive analytics, time-series modeling, NLP, and decision-support systems in high-stakes financial environments. Across KakaoPay and Kyobo Life, I have built predictive models, monitoring frameworks, automated data pipelines, and business-facing reporting systems using Python, R, SQL, and statistical modeling. This project translates that core workflow into an aerospace-style operational analytics problem.

## Dataset
- **Source**: NASA CMAPSS Turbofan Engine Degradation Simulation Dataset
- **Scenario used**: FD001
- **Data type**: multivariate time-series
- **Prediction target**: Remaining Useful Life (RUL)

The dataset contains:
- engine unit ID
- time cycle
- operational settings
- multiple sensor measurements across engine operating cycles

## Problem Statement
Aircraft engine maintenance is a classic decision-support problem under uncertainty.  
The objective is to estimate how many operating cycles remain before an engine reaches a failure threshold, then translate that prediction into a practical maintenance recommendation.

In this prototype:
- the model predicts RUL for each engine
- the final-cycle prediction is used to estimate urgency
- a maintenance brief is generated to support human interpretation

## Project Structure
```bash
boeing-predictive-maintenance/
├─ data/
│  ├─ train_FD001.txt
│  ├─ test_FD001.txt
│  └─ RUL_FD001.txt
├─ notebooks/
│  └─ boeing_predictive_maintenance.ipynb
├─ outputs/
│  ├─ fd001_test_predictions.csv
│  └─ sample_engine_maintenance_report.md
├─ README.md
└─ requirements.txt
