# Patient dropout and retention risk modelling in clinical trials
Predictive patient dropout and retention risk modeling using longitudinal clinical trial data (Kaggle) with machine learning, survival analysis, and SHAP interpretability.

## Overview
Patient attrition during clinical trials poses significant financial, operational, and regulatory challenges, often degrading statistical power and delaying drug approval timelines. 
This repository provides an end-to-end data science pipeline to predict patient dropout risk and model longitudinal retention patterns using synthetic multi-visit clinical trial data (`longitudinal_visits_demo_1000.csv`). By analyzing patient-level trajectories—including biomarker deltas (e.g., $\Delta\text{HbA1c}$), adverse event accumulation, and inter-visit gap variances—this project enables Clinical Operations (ClinOps) teams to implement targeted, proactive retention interventions.

## Key Features & Workflow
- **Longitudinal Data Ingestion & ETL**: Cleans multi-row visit histories, validates temporal order, and audits missingness patterns (MCAR vs. MNAR).
- **Clinical Feature Engineering**: Aggregates longitudinal visit streams into static patient-level vectors (baseline values, trajectory slopes, compliance rates, and adverse event counts).
- **Predictive Machine Learning**: Evaluates baseline Logistic Regression, Random Forest, XGBoost, and LightGBM models using stratified group splitting to avoid site-level data leakage.
- **Time-to-Event Survival Analysis**: Implements Kaplan-Meier curves and Cox Proportional Hazards models to estimate retention probabilities across trial duration.
- **Explainability & Risk Stratification**: Utilizes SHAP (Shapley Additive exPlanations) to identify primary dropout drivers and stratify patients into actionable risk tiers (Low, Moderate, High).

## Tech Stack & Libraries
- **Language**: Python 3.10+
- **Data Manipulation**: `pandas`, `numpy`
- **Machine Learning**: `scikit-learn`, `lightgbm`, `xgboost`
- **Survival Analysis**: `lifelines`
- **Interpretability**: `shap`
- **Visualization**: `matplotlib`, `seaborn`
