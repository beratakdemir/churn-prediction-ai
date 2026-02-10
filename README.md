# End-to-End Customer Churn Prediction (Machine Learning)

## 📌 Project Overview
Customer churn is one of the most critical challenges for subscription-based businesses.  
In this project, I built an **end-to-end churn prediction system** using machine learning, with a strong focus on **business impact**, **model interpretability**, and **decision threshold optimization**.

Rather than maximizing accuracy alone, the model is optimized to **minimize missed churn cases**, which is often more valuable in real-world retention strategies.

---

## 🎯 Business Objective
The primary goal of this project is to:

- Identify customers who are likely to churn
- Reduce missed churn cases (False Negatives)
- Provide **actionable insights** that can be used by business and retention teams

This mirrors real-world scenarios where **recall on churned customers** is more important than raw accuracy.

---

## 🧠 Dataset
- **Source:** Kaggle – Telco Customer Churn Dataset  
- **Size:** 7,043 customers  
- **Target Variable:** `Churn` (Yes / No)

### ⚠️ Dataset Handling
The dataset is intentionally **excluded from version control** using `.gitignore`.  
To run the project locally, the dataset must be downloaded separately from Kaggle.

---

## 🛠️ Tools & Technologies
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook
- Git & GitHub

---

## 🔄 Project Workflow

### 1️⃣ Data Exploration & Cleaning
- Inspected data types and distributions
- Converted `TotalCharges` to numeric format
- Handled missing values
- Analyzed churn distribution and class imbalance

---

### 2️⃣ Feature Engineering
- One-hot encoded categorical variables
- Removed identifiers (`customerID`)
- Standardized features where necessary
- Prepared modeling-ready feature matrix

---

### 3️⃣ Model Development
- Baseline model: **Logistic Regression**
- Applied `class_weight="balanced"` to handle class imbalance
- Trained and evaluated on a held-out test set

---

### 4️⃣ Threshold Optimization (Key Step)
Instead of using the default `0.5` decision threshold, I **manually tuned the threshold** to optimize for churn recall.

This allows the model to:
- Catch more churn-prone customers
- Accept a controlled increase in false positives

📌 **Chosen Threshold:** `0.40`

---

### 5️⃣ Model Evaluation
The model was evaluated using multiple metrics to reflect real-world priorities.

#### Key Results (Recall-Optimized):
- **Accuracy:** ~0.70
- **Recall (Churn = 1):** ~0.88
- **Precision (Churn = 1):** ~0.47
- **ROC-AUC:** ~0.86

These results demonstrate a deliberate trade-off:
> Lower accuracy in exchange for significantly fewer missed churn cases.

---

## 🔍 Model Explainability
To ensure transparency and business interpretability, I analyzed **Logistic Regression coefficients**.

### Key Insights:
- Long-term contracts (1-year, 2-year) significantly reduce churn risk
- Fiber optic internet customers show higher churn likelihood
- Customers without online security or tech support are more likely to churn
- Electronic check payment method is associated with higher churn

These insights can directly inform:
- Retention campaigns
- Pricing strategies
- Service bundling decisions

---

## 📊 Visual Summary
The project includes a full professional visualization suite:
- Churn distribution analysis
- Recall-optimized confusion matrix
- Key churn drivers (feature importance)
- Precision–recall threshold trade-off
- Model comparison table

All visuals are generated programmatically and stored in the `images/` directory.

---

## 🚀 Key Takeaways
- Accuracy alone is not sufficient for churn problems
- Threshold tuning can dramatically improve business outcomes
- Explainable models are often more valuable than complex black-box models
- This project demonstrates a **business-first machine learning mindset**

---

## 🔧 How to Run Locally
1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
