# Airline Passenger Satisfaction Analysis

This repository contains a complete end‑to‑end analysis and prediction project using the **Airline Passenger Satisfaction** dataset. The goal is to explore what drives customer satisfaction and build machine‑learning models to predict whether a passenger is satisfied.

---

## 🚀 Project Overview

This project includes:

- Data cleaning & manipulation  
- Exploratory data analysis (EDA)  
- Visualization of key satisfaction factors  
- Correlation analysis  
- Feature encoding and scaling  
- Multiple ML models and performance comparison  
- Cross‑validation (regular + limited‑hyperparameter CV to address overfitting)  
- Feature importance interpretation  

---

## 📁 Notebook Workflow

### **1. Data Manipulation**
- Managed missing values
- Cleaned inconsistent entries
- Encoded categorical features (Label Encoding)
- Prepared data for modeling

### **2. Visualization**
The notebook includes dozens of plots covering:

- Satisfaction by **Gender**
- Effect of **Arrival & Departure Delays**
- Satisfaction breakdown by **Customer Type**, **Travel Type**, and **Class**
- **Age distribution** and its impact on satisfaction
- Age vs service ratings (Gate Location, Wifi Service, Entertainment)
- Investigation into whether **older passengers were more dissatisfied** on long‑distance flights

### **3. Correlation Analysis**
A correlation heatmap highlights relationships between numerical features such as:
- Inflight Entertainment
- Seat Comfort
- Cleanliness
- On‑board Service  
…and more.

These help identify which service metrics align strongly with satisfaction.

---

## 🔧 Feature Engineering

- **Label Encoding** for categorical variables  
- **StandardScaler** applied to numerical features  

📌 **Important Finding:**  
Logistic Regression performed **significantly better** after scaling → demonstrates the importance of normalization for linear models.

---

## 🤖 Machine Learning Models

The following ML models were built and compared:

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

### **Model Evaluation**
- Accuracy  
- Precision  
- Recall  
- F1‑Score  
- ROC‑AUC  
- Confusion Matrices  

### **Cross‑Validation**
Two rounds were performed:
1. **Initial cross‑validation** → some models were overfitting  
2. **Cross‑validation with limited hyperparameters** → more stable performance  

### ⭐ **Best Model**
**AdaBoost** achieved the highest performance in cross‑validation and was selected as the best model.

A **feature importance bar chart** was generated for the final model.

---

## 📝 Business Questions Answered

The notebook includes complete answers + visualizations for:

1. Which gender is more/less satisfied?
2. Satisfaction among delayed flights.
3. How Class, Customer Type, and Travel Type affect satisfaction.
4. Age distribution patterns.
5. Age vs service ratings (Wifi, Entertainment, Gate Location).
6. Whether older passengers are more dissatisfied due to long‑distance flights.

---

## 📊 Key Insights

- Service quality variables (Inflight Entertainment, Seat Comfort, On‑board Service) show strong correlation with satisfaction.
- Older passengers show distinct patterns in service expectations.
- Scaling greatly improved Logistic Regression.
- AdaBoost and Gradient Boosting consistently performed well.
- Cross‑validation helped reduce overfitting and improved reliability.

---

## 🧪 Technologies Used

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit‑Learn  
- XGBoost  

---

## 📂 File Structure

```
Airline Satisfaction.ipynb
README.md  ← This file
```

---

## ▶️ How to Run

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Launch the notebook:
   ```bash
   jupyter notebook "Airline Satisfaction.ipynb"
   ```

---

## 🧭 Future Improvements

- Tune AdaBoost and Gradient Boosting with GridSearch/RandomSearch
- Add LightGBM / CatBoost models
- Build a dashboard using Streamlit/Plotly Dash
- Deploy the final model as an API

---

## 📬 Contact

Feel free to reach out for improvements or questions!

