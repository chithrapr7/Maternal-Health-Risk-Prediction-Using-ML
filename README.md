# 🩺 Maternal Health Risk Prediction using Machine Learning

## 📌 Problem Statement

Maternal mortality remains a serious global health issue, with approximately **287,000 deaths annually worldwide**.

Many of these deaths are preventable with **early risk detection and timely medical intervention**. However, identifying high-risk pregnancies manually can be difficult and time-consuming.

👉 This project aims to leverage **Machine Learning** to classify maternal health risk levels into:
- Low Risk
- Mid Risk
- High Risk

based on key physiological parameters.

---

## 🎯 Objective

- Build an accurate and interpretable **multi-class classification model**
- Identify **high-risk patients early**
- Assist healthcare professionals in **decision-making**
- Reduce complications through **data-driven screening**

---

## 📊 Dataset Overview

- **Source:** UCI Machine Learning Repository  
- **Total Records:** 1,014 patients  
- **Features:** 6 input variables  
- **Target:** RiskLevel (Low / Mid / High)  
- **Missing Values:** None  

### Features Description

| Feature        | Description                          | Unit     |
|----------------|--------------------------------------|----------|
| Age            | Patient age                          | Years    |
| SystolicBP     | Upper blood pressure                 | mmHg     |
| DiastolicBP    | Lower blood pressure                 | mmHg     |
| BS             | Blood sugar level                    | mmol/L   |
| BodyTemp       | Body temperature                     | °F       |
| HeartRate      | Heart rate                           | bpm      |

### Class Distribution

- Low Risk: 406  
- Mid Risk: 336  
- High Risk: 272  

---

## 🔍 Exploratory Data Analysis (EDA)

- Class imbalance identified → handled using **SMOTE**
- Strong correlation observed between:
  - SystolicBP & DiastolicBP
- Feature distributions analyzed using:
  - Histograms
  - Violin plots

---

## ⚙️ Data Preprocessing Pipeline

To ensure robust and leakage-free modeling:

1. Removed duplicate records  
2. Performed **80-20 stratified train-test split**  
3. Applied **IQR method for outlier removal (train set only)**  
4. Encoded target variable using **Label Encoding**  
5. Applied **StandardScaler** (fit on train, transform on test)  
6. Balanced data using **SMOTE (train set only)**  

✅ **Key Principle:** No data leakage — all transformations applied only on training data.

---

## 🤖 Model Building

Five machine learning models were implemented:

- Logistic Regression (Baseline)
- Decision Tree
- Random Forest
- K-Nearest Neighbors (KNN)
- XGBoost ⭐

### Validation Strategy

- **5-Fold Cross Validation**
- Evaluation on **unseen test data**

---

## 📈 Model Performance

| Model                  | Accuracy | F1-Score | ROC-AUC | CV Score |
|------------------------|----------|----------|---------|----------|
| Logistic Regression    | ~72%     | ~0.71    | ~0.85   | ~0.78    |
| Decision Tree          | ~80%     | ~0.80    | ~0.88   | ~0.81    |
| Random Forest          | ~85%     | ~0.84    | ~0.93   | ~0.85    |
| K-Nearest Neighbors    | ~78%     | ~0.77    | ~0.89   | ~0.79    |
| **XGBoost (Best)** ⭐   | **~87%** | **~0.87**| **~0.96**| **~0.87**|

---

## 🔧 Hyperparameter Tuning

Used **GridSearchCV** to optimize models:

- Logistic Regression → `C`, `solver`
- Decision Tree → `max_depth`, `min_samples`
- Random Forest → `n_estimators`, `max_depth`
- XGBoost → `learning_rate`, `max_depth`, `n_estimators`

---

## 🏆 Key Findings

- **XGBoost outperformed all models**
- **Blood Sugar (BS)** and **SystolicBP** are the strongest predictors
- Ensemble models > Linear models
- Proper preprocessing + SMOTE improved performance significantly

---

## 🏥 Real-World Impact

- Enables **early detection of high-risk pregnancies**
- Helps prioritize **critical medical attention**
- Useful in **resource-limited healthcare settings**
- Can contribute to reducing global maternal mortality

---

## 📌 Conclusion

This project demonstrates a complete **end-to-end Machine Learning pipeline**, including:

- Data Cleaning & EDA  
- Feature Engineering  
- Model Training & Evaluation  
- Hyperparameter Tuning  

👉 The final **XGBoost model achieved ~96% ROC-AUC**, making it highly effective for risk classification.

Machine Learning can play a critical role in **preventive healthcare**, especially in maternal risk assessment.

---
