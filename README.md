# ai-leadership-trust-analysis
OLS regression, regression trees, propensity score matching, and causal inference to model trust in AI-assisted leadership using Python

## Overview

This project analyzes a 5,500-row dataset of organizational AI adoption to understand what predicts employee trust in AI-assisted leadership. The analysis builds and compares multiple predictive models, addresses multicollinearity, and applies causal inference methods to test whether data privacy compliance drives higher trust scores.

## Methods

- **OLS Regression:** Built simple, multiple, and nonlinear OLS models to predict leadership trust scores. Best model achieved R² = 0.477 on held-out test data (RMSE = 9.92)
- **Multicollinearity Check:** Ran VIF analysis across predictors. Applied PCA to resolve high-collinearity variables before modeling
- **Model Comparison:** Evaluated OLS against a regression tree using train/test split and 5-fold cross-validation, OLS outperformed on test RMSE
- **Propensity Score Matching (PSM):** Applied PSM with caliper (.05) to estimate the causal effect of data privacy compliance on trust scores. Checked covariate balance using standardized mean differences (SMD)
- **Causal Decision Tree:** Built a causal tree to explore heterogeneous treatment effects across subgroups

## Key Findings

- OLS regression outperformed the regression tree on held-out data (test RMSE: 9.92 vs. 12.17 for regression tree)
- Organizations with data privacy compliance scored 17.6 points higher on leadership trust after controlling for confounders via PSM
- PCA was necessary to address multicollinearity among correlated predictors before stable OLS estimation

## Tech Stack

Python, pandas, scikit-learn, statsmodels, matplotlib

## Data Source

[AI Adoption and Leadership Trust Dataset](https://www.kaggle.com/datasets/mexwell/ai-in-business-adoption-leadership-and-trust) — Kaggle
