# 🚰 Water Pump Functionality Prediction

A machine learning project to predict whether water pumps are **Functioning** or **Not Functioning** — helping prioritize maintenance and reduce downtime in water infrastructure.

---

## 📌 Problem Statement

Access to clean water is critical. Many water pumps fail silently, leaving communities without water. This project builds a predictive model to identify non-functional pumps before manual inspection, enabling data-driven maintenance planning.

---

## 📊 Dataset Overview

| Property | Value |
|----------|-------|
| Total Records | 5,000 |
| Features | 12 |
| Target Classes | Functioning / Not Functioning |
| Class Imbalance | 78.6% Not Functioning, 21.4% Functioning |

**Key Features:**
- Water Source Type, Water Quality
- Distance to Nearest Town
- Population Served
- Installation Year, Water Pump Age
- Pump Type, Funder, Payment Type
- GPS Coordinates

---

## 🛠️ Tech Stack
Python | Pandas | NumPy | Scikit-learn | Imbalanced-learn | Matplotlib | Seaborn

---

## 🔄 Workflow
Raw Data → EDA → Data Cleaning → Feature Engineering → Class Imbalance Handling → Model Training → Evaluation

---

## ⚙️ Feature Engineering

| Feature | Description |
|---------|-------------|
| Latitude, Longitude | Extracted from GPS Coordinates |
| Population Density | Population Served / Distance to Town |
| Missing Indicators | Binary flags for Unknown categorical values |

**Final feature count: 17**

---

## 🤖 Models & Results

| Rank | Model | Accuracy | F1-Score | ROC AUC |
|------|-------|----------|----------|---------|
| 🥇 1 | Random Forest (Optimized) | **79.02%** | **77.16%** | **0.777** |
| 🥈 2 | Gradient Boosting (Optimized) | 78.80% | 78.10% | 0.776 |
| 🥉 3 | Logistic Regression | 67.92% | 70.63% | 0.745 |
| 4 | Support Vector Machine | 65.10% | 68.13% | 0.726 |
| 5 | K-Nearest Neighbors | 62.29% | 65.49% | 0.647 |

---

## 🏆 Best Model — Random Forest (Optimized)

**Hyperparameters (via GridSearchCV):**
- n_estimators = 100
- max_depth = 20
- min_samples_split = 5
- min_samples_leaf = 2
- class_weight = balanced

**Performance:**
- Test Accuracy: 79.02%
- Cross-Validation Accuracy: 77.43% (±1.11%)
- ROC AUC: 0.777

---

## 🔍 Top Predictive Features

| Rank | Feature | Importance |
|------|---------|------------|
| 1 | Pump Type | 13.3% |
| 2 | Water Source Type | 12.3% |
| 3 | Population Density | 10.8% |
| 4 | Latitude | 10.3% |
| 5 | Longitude | 9.9% |
| 6 | Distance to Nearest Town | 7.3% |
| 7 | Water Pump Age | 6.8% |
| 8 | Installation Year | 6.8% |

---

## 💡 Key Insights

- **Geographic location** is a strong predictor — pump failures cluster in specific regions
- **Older pumps** are significantly more likely to be non-functional
- **Pump Type** is the single most important feature — motorized vs solar vs hand pumps have very different failure rates
- **SMOTE oversampling** improved minority class detection compared to imbalanced training

---

## 📈 Business Impact

- Proactively identify at-risk pumps **before** they fail
- Prioritize maintenance routes by geographic cluster
- Reduce response time and operational costs
- Improve water access reliability for served communities

---

