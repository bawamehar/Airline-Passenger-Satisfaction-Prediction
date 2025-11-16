# ✈️ Airline Passenger Satisfaction — Predictive Analysis

[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](./Airline%20Satisfaction.ipynb) [![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)]() [![scikit-learn](https://img.shields.io/badge/scikit--learn-%3E%3D0.24-yellowgreen?logo=scikit-learn)]() [![XGBoost](https://img.shields.io/badge/XGBoost-%3E%3D1.0-lightgrey)]()  
[![License](https://img.shields.io/badge/License-MIT-brightgreen)]()

---

A polished, end‑to‑end exploration and classification project to understand **what drives airline passenger satisfaction** and to build models that predict whether a passenger is satisfied.

---

## ✨ Highlights (TL;DR)

- Applied **data cleaning**, **EDA**, **feature engineering**, and **visualization** to uncover satisfaction drivers.
- Built and compared several models: **Logistic Regression, Decision Tree, Random Forest, Gradient Boosting, AdaBoost, XGBoost**.
- **AdaBoost** emerged as the best-performing model after careful cross-validation.
- Important discovery: **Logistic Regression improved significantly after applying `StandardScaler`** → scaling matters for linear models.
- Produced model interpretation via **feature importance** charts (AdaBoost).

---

## 📚 Table of Contents

1. [Project Overview](#project-overview)  
2. [Notebook Workflow](#notebook-workflow)  
3. [Models & Evaluation](#models--evaluation)  
4. [Top Insights](#top-insights)  
5. [How to run](#how-to-run)  
6. [What to try next](#what-to-try-next)  
7. [Files](#files)  
8. [Contact](#contact)

---

## 🧭 Project Overview

This notebook analyzes the *Airline Passenger Satisfaction* dataset to answer business questions such as:

- Which passenger groups are more/less satisfied?
- How do delays and class affect satisfaction?
- Which service metrics (e.g., seat comfort, entertainment) matter most?

It also trains multiple classifiers to predict passenger satisfaction and interprets the results.

---

## 🛠️ Notebook Workflow

**1. Data cleaning**
- Handle missing and inconsistent values
- Remove or transform irrelevant fields

**2. Feature engineering**
- Label encoding of categorical features
- Derived variables where useful

**3. Scaling**
- Applied `StandardScaler` to numeric features
- Observed large gain for Logistic Regression after scaling

**4. EDA & Visuals**
- Bar plots, histograms, and heatmaps:
  - Satisfaction by Gender, Class, Customer Type, Travel Type
  - Arrival/Departure delay vs satisfaction
  - Age distribution and service-rating relationships

**5. Modeling**
- Trained the set of models below
- Ran cross-validation twice (initial CV → overfitting observed, then CV with constrained hyperparameter ranges)

---

## 🤖 Models (implemented)

```python
models = {
    'Logistic Regression': LogisticRegression(max_iter=1000),
    'Decision Tree': DecisionTreeClassifier(random_state=52),
    'Random Forest': RandomForestClassifier(random_state=52),
    'gradient boost': GradientBoostingClassifier(random_state=52),
    'adaboost': AdaBoostClassifier(random_state=52),
    'XGBoost': XGBClassifier(eval_metric='logloss')
}
```

**Evaluation metrics used:** Accuracy, Precision, Recall, F1‑score, ROC‑AUC, Confusion Matrix

**Best model (after CV):** `AdaBoost` — chosen based on cross‑validated performance and stability after hyperparameter constraints.

---

## 🔍 Top Insights & Takeaways

- **Scaling matters.** Logistic Regression's performance increased noticeably after applying `StandardScaler`.
- **Service metrics drive satisfaction.** Features like *Inflight Entertainment*, *Seat Comfort*, and *On-board Service* show strong correlation with satisfaction.
- **Age patterns exist.** Older passengers show different expectation patterns; investigate targeted service improvements.
- **Overfitting check.** Running CV twice (and restricting hyperparameter ranges) reduced overfitting and produced more reliable results.
- **Feature importance.** AdaBoost’s feature importance plot highlights the top predictors — include those in business action plans.

---

## 📈 Example Visuals (in the notebook)
- Satisfaction breakdown (by Class / Gender / Customer Type)  
- Heatmap of correlations  
- Delay vs Satisfaction scatter / box plots  
- Feature importance bar chart (AdaBoost)

---

## ▶️ How to run

```bash
# clone
git clone <your-repo-url>
cd <repo-folder>

# recommended: create virtual env
python -m venv venv
source venv/bin/activate   # Linux / macOS
venv\Scripts\activate    # Windows PowerShell

# install
pip install -r requirements.txt

# open notebook
jupyter notebook "Airline Satisfaction.ipynb"
```

**Suggested `requirements.txt` minimal entries**
```
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
jupyter
```

---

## 🧪 Reproducibility notes

- Set random seeds (e.g., `random_state=52`) used in tree-based models for reproducible results.
- When re-running experiments, ensure the same preprocessing pipeline (label encoders + scaler) is applied to train and test folds.
- Cross-validation: use `StratifiedKFold` to maintain class balance across folds for classification stability.

---

## 🚀 Next steps / Improvements

- Full hyperparameter tuning with `GridSearchCV` / `RandomizedSearchCV` for AdaBoost & XGBoost
- Try LightGBM / CatBoost for speed and categorical handling
- Create a **Streamlit** demo to explore model predictions interactively
- Save the final pipeline with `joblib` / `pickle` and expose a small Flask API

---

## 📁 Project Files

- `Airline Satisfaction.ipynb` — The full notebook (EDA, modeling, plots)  
- `README.md` — This file  
- `requirements.txt` — Python dependencies

---

## 🤝 Credits & Contact

Created by you — for collaboration or questions, open an issue or email me!

---

*If you want, I can add:*
- a compact project badge panel,  
- an example GIF of the notebook plots (placeholder), or  
- a short `results.md` snippet that includes the exact CV metrics and confusion matrices from your run.  
Tell me which and I'll update the README.
