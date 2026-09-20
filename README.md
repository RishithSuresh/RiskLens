# Credit Card Default Prediction — IDRA Capstone Project

## Overview

This project develops and evaluates classification models for predicting next-month credit card default using the **UCI Taiwan Credit Card dataset** (30,000 customer records). It was completed as part of the **India Data Research Academy (IDRA)** Data Science and AI internship capstone.

## Problem Statement

> Can customer demographic, repayment-status, billing, and payment behavior predict whether a credit-card account will default in the following month?

## Key Results

| Model | ROC-AUC | PR-AUC | Balanced Accuracy |
|---|---|---|---|
| **Hist-gradient boosting** | **0.777** | **0.549** | **0.656** |
| Random forest | 0.775 | 0.547 | 0.644 |
| Logistic regression | 0.740 | 0.479 | 0.653 |
| Dummy baseline | 0.500 | 0.221 | 0.500 |

- **Best model**: Histogram Gradient Boosting Classifier
- **Strongest predictor**: PAY_0 (most recent repayment status)
- **Default rate**: 22.12% (imbalanced classification)

## Project Structure

```
RiskLens/
├── P_5_UCI_Credit_Card.csv                          # Source dataset (UCI Taiwan)
├── credit_card_default_capstone.ipynb               # Full analysis notebook
├── credit_card_default_capstone.html                # HTML export of notebook
├── credit_card_default_capstone_report_final.docx   # IDRA capstone report
├── figures/                                         # Generated charts
│   ├── figure_1_target_distribution.png
│   ├── figure_2_repayment_default.png
│   ├── figure_3_credit_limit_default.png
│   ├── figure_4_correlation_heatmap.png
│   ├── figure_5_confusion_matrix.png
│   └── figure_6_threshold_tradeoff.png
└── artifacts/                                       # Model evaluation artifacts
```

## Methodology

1. **Data Understanding** — Profiling, missing values, duplicates, target prevalence
2. **Data Cleaning** — Column standardization, identifier exclusion, category validation
3. **Preprocessing** — StandardScaler for numeric features, OneHotEncoder for categorical features, applied inside scikit-learn pipelines to prevent data leakage
4. **EDA** — Target distribution, repayment behavior analysis, correlation heatmap
5. **Statistical Analysis** — Chi-square tests (categorical), Mann-Whitney U tests (numerical)
6. **Model Development** — Four classifiers compared: Dummy baseline, Logistic Regression, Random Forest, Histogram Gradient Boosting
7. **Model Evaluation** — PR-AUC, ROC-AUC, balanced accuracy, confusion matrix, permutation importance
8. **Threshold Analysis** — F2-optimized threshold (0.12) vs default threshold (0.50)

## Tech Stack

- **Python 3.12+**
- **pandas** — Data manipulation
- **scikit-learn** — Preprocessing pipelines, model training, evaluation
- **matplotlib / seaborn** — Visualization
- **python-docx** — Report generation

## Dataset

- **Source**: [UCI Machine Learning Repository — Default of Credit Card Clients](https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients)
- **Reference**: Yeh, I-C. and Lien, C-H. (2009). *The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients.* Expert Systems with Applications, 36(2), 2473–2480.

## Setup

```bash
# Create virtual environment
python -m venv .venv

# Activate (Windows)
.venv\Scripts\activate

# Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn python-docx jinja2 jupyter
```

## Usage

```bash
# Run the notebook
jupyter notebook credit_card_default_capstone.ipynb
```

## License

This project was completed for academic purposes as part of the IDRA Data Science and AI internship program.
