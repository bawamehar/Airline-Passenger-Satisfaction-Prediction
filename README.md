# Airline Passenger Satisfaction Analysis

This repository contains two complete end‑to‑end projects on the Airline
Passenger Satisfaction dataset:\
1. A **Python (Jupyter Notebook) project** performing full EDA,
modeling, and boosting-based ML experiments.\
2. A **KNIME Analytics Platform project** developed for coursework,
following a structured data‑mining workflow and restricted to
non‑boosting models.

Both projects explore what drives customer satisfaction and build
predictive models to classify whether a passenger is satisfied.

---

## 🚀 Project Overview

This project includes:

- Data cleaning & manipulation  
- Exploratory data analysis (EDA)  
- Visualization of key satisfaction factors [using Python]
- Correlation analysis  
- Feature encoding and scaling  
- Multiple ML models and performance comparison  
- Cross‑validation (regular + limited‑hyperparameter CV to address overfitting) [using Pyton]  
- Feature importance interpretation [using Pyton] 

---

## 📁 Notebook Workflow

---

## 1️⃣ Python (Jupyter Notebook) Project

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

### **4. Feature Engineering**

- **Label Encoding** & **One-Hot Encoding** for categorical variables  
- **StandardScaler** applied to numerical features  

📌 **Important Finding:**  
Logistic Regression performed **significantly better** after scaling → demonstrates the importance of normalization for linear models.

### **5. Machine Learning Models**

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

### **5. Model Evaluation**
- Accuracy  
- Precision  
- Recall  
- F1‑Score  
- ROC‑AUC  
- Confusion Matrices  

### **6. Cross‑Validation**
Two rounds were performed:
1. **Initial cross‑validation** → some models were overfitting  
2. **Cross‑validation with limited hyperparameters** → more stable performance  

### ⭐ **Best Model**
**AdaBoost** achieved the best performance overall in cross‑validation and was selected as the best model.

A **feature importance bar chart** was generated for the final model.

---

## 2️⃣ KNIME Analytics Platform Project

*(Built for CIS 575 coursework --- boosting algorithms not allowed, so
tree‑based and neural network models were emphasized.)*

### **1. Data Preparation**

-   Imported via CSV Reader\
-   Removed invalid rows (e.g., 0 ratings where invalid)\
-   Missing values imputed using Mode\
-   One‑to‑Many (one‑hot) encoding for categorical variables\
-   Numerical features normalized\
-   Train/validation split using Partitioning nodes

###  **2. Machine Learning Models (KNIME)**

-   Logistic Regression (with/without normalization)\
-   Decision Tree (standard + pruned using MDL pruning)\
-   Random Forest\
-   Neural Network (baseline + optimized MLP)

### ⭐ **Best Model (KNIME)**

**Random Forest** --- highest accuracy (95.76%) + excellent recall for
dissatisfied passengers.

---

### 📝 Business Questions Answered

The notebook includes complete answers + visualizations for:

1. Which gender is more/less satisfied?
2. Satisfaction among delayed flights.
3. How Class, Customer Type, and Travel Type affect satisfaction.
4. Age distribution patterns.
5. Age vs service ratings (Wifi, Entertainment, Gate Location).
6. Whether older passengers are more dissatisfied due to long‑distance flights.

---

## 📊 Key Insights

- Service quality variables (Inflight Entertainment, Seat Comfort, Online Boarding, Inflight Wi‑Fi) show strong correlation with satisfaction.
- Older passengers show distinct patterns in service expectations.
- Scaling greatly improved Logistic Regression.
- AdaBoost and Gradient Boosting consistently performed well.
- Cross‑validation helped reduce overfitting and improved reliability.
- Longer arrival & departure delays increase dissatisfaction probability.

---

## 📊 Summary

The corelation heatmap clearly shows that personal traveller and class:eco columns are negatively related to Leg room service, Seat comfort and flight distance. This makes sense because economy passengers typically experience smaller seat space and less legroom. Moreover, Personal travelers tend to be more emotionally sensitive to these limitations as they Pay out-of-pocket and therefore have higher expectations for value. Their travel is often leisure-related, so discomfort has a stronger impact on perceived satisfaction.

All these reasons are enough for both "Type of travel" and "Class Eco" features show strong negative correlations with the Satisfaction column. They represent groups that experience lower comfort and higher emotional sensitivity, making them more likely to report dissatisfaction.

---

## 🧪 Technologies Used

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit‑Learn  
- XGBoost
- KNIME Analytics Platform  

---

## 📬 Contact

Feel free to reach out for improvements or questions!

