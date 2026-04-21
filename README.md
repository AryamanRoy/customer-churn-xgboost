# Customer Churn Prediction

This project builds a machine learning model to predict customer churn using behavioral usage data, subscription information, and engineered features. The goal is to identify users who are likely to churn so that proactive retention strategies can be applied.

---

## Overview

Customer churn prediction is a common problem in SaaS and subscription-based businesses. This project uses historical user activity and subscription data to train a model that estimates the likelihood of churn.

The pipeline includes:
- Data preprocessing and merging
- Feature engineering (behavioral, temporal, and usage-based)
- Model training using XGBoost
- Evaluation using ROC-AUC and Precision-Recall metrics
- Threshold tuning for practical classification

---

## Dataset

This project uses three datasets:

- `ravenstack_feature_usage.csv`
- `ravenstack_churn_events.csv`
- `ravenstack_subscriptions.csv`

These files are not included in the repository due to size and/or privacy concerns.

Place the datasets inside the `data/` folder before running the notebook.

Expected structure:

```

data/
├── ravenstack_feature_usage.csv
├── ravenstack_churn_events.csv
└── ravenstack_subscriptions.csv

```

---

## Project Structure

```

CHURN/
├── data/                 # Dataset (not included)
├── notebooks/            # Jupyter notebooks
│   └── churn_pred.ipynb
├── README.md
├── requirements.txt
└── .gitignore

```

---

## Features Used

The model uses a combination of:

- Usage metrics (activity, duration, error counts)
- Rolling statistics (mean, standard deviation, trends)
- Behavioral indicators (inactivity, drop in usage)
- Feature usage diversity (number of features used, usage distribution)
- Subscription attributes (plan type, upgrades/downgrades, billing patterns)

---

## Model

- Model: XGBoost Classifier
- Objective: Binary classification (churn vs non-churn)
- Evaluation metrics:
  - ROC-AUC
  - Precision-Recall AUC
  - Precision, Recall, F1-score

Threshold tuning is applied to balance precision and recall based on business needs.

---

## Results

Typical performance achieved:

- ROC-AUC: ~0.93–0.94
- PR-AUC: ~0.48–0.50
- Precision (churn class): ~0.40–0.50
- Recall (churn class): ~0.50–0.55

These results indicate strong ranking ability and reasonable classification performance for an imbalanced dataset.

---

## How to Run

1. Install dependencies:

```

pip install -r requirements.txt

```

2. Place datasets in the `data/` folder.

3. Open the notebook:

```

notebooks/churn_pred.ipynb

```

4. Run all cells.

---

## Key Insights

- Behavioral trends are more predictive than raw usage counts
- Feature usage diversity is a strong indicator of churn risk
- Model performance is highly dependent on feature engineering
- Threshold selection significantly impacts classification results

---

## Limitations

- Dataset is synthetic or limited in scope
- No real-time prediction pipeline
- Temporal modeling is simplified (aggregated features)

---

## Future Improvements

- Add time-window based modeling (last 7/30 days)
- Incorporate sequence models (LSTM/Transformers)
- Add model explainability (SHAP)
- Deploy as an API or dashboard (Streamlit)
- Perform hyperparameter optimization and cross-validation

---

## License

This project is for educational and demonstration purposes.
```

---

