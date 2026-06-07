# 🚗 Automobile-Price-Predictor
A complete data science capstone project that builds a predictive model for automobile pricing using regression and ensemble techniques. The analysis covers EDA, preprocessing, multi-model comparison, and business insights.

---

## 📋 Problem Statement

Model the price of cars using available independent variables to help management:
- Understand how prices vary with car specifications
- Manipulate design and business strategy to meet target price levels
- Understand pricing dynamics in new markets

## 📁 Project Structure

```
AutoPricePred/
│
├── auto_imports.csv                  # Raw dataset (201 records, 26 features)
├── PRCP_1017_AutoPricePred.py        # Main analysis script (Tasks 1 & 2)
├── AutoPricePred_Report.docx         # Full data analysis & model comparison report
└── README.md                         # Project documentation
```
---

## 📊 Dataset

- **Source:** [PRCP-1017 Dataset](https://d3ilbtxij3aepc.cloudfront.net/projects/CDS-Capstone-Projects/PRCP-1017-AutoPricePred.zip)
- **Records:** 201 automobiles
- **Features:** 26 (25 predictors + 1 target)
- **Target:** `price` — continuous variable ($5,118 – $45,400)
- **Brands covered:** 22 makes including BMW, Toyota, Honda, Mercedes-Benz, Porsche, and more

### Key Features

| Feature | Type | Description |
|---|---|---|
| `make` | Categorical | Car brand/manufacturer |
| `engine-size` | Continuous | Engine displacement |
| `horsepower` | Continuous | Engine power output |
| `curb-weight` | Continuous | Vehicle weight |
| `fuel-type` | Categorical | Diesel or Gas |
| `body-style` | Categorical | Sedan, Hatchback, Convertible, etc. |
| `city-mpg` / `highway-mpg` | Continuous | Fuel efficiency |
| `price` | Continuous | **Target variable** |

---

## 🔍 Tasks

### Task 1 — Data Analysis Report
- Exploratory Data Analysis (EDA) with visualizations
- Missing value analysis (normalized-losses had 18.4% missing)
- Correlation heatmap and feature relationships
- Distribution and bivariate analysis of key variables

### Task 2 — Predictive Modeling
Six regression models trained and evaluated:

| Model | R² | RMSE ($) | MAE ($) |
|---|---|---|---|
| **Gradient Boosting** ⭐ | **0.9512** | **2,444** | **1,505** |
| Random Forest | 0.9365 | 2,787 | 1,775 |
| Decision Tree | 0.9342 | 2,838 | 1,923 |
| Lasso Regression | 0.8590 | 4,153 | 2,788 |
| Ridge Regression | 0.8555 | 4,205 | 2,853 |
| Linear Regression | 0.8535 | 4,233 | 2,804 |

> ✅ **Best Model: Gradient Boosting Regressor** — R² of 0.9512 with the lowest RMSE and MAE.

---

## 🔧 Top Price Drivers (Feature Importance)

1. `engine-size` — strongest predictor of price
2. `curb-weight` — heavier cars cost more
3. `horsepower` — performance correlates with price
4. `highway-mpg` / `city-mpg` — fuel efficiency inversely related to price
5. `width` — larger vehicles skew premium

---

## ⚠️ Challenges & Solutions

| Challenge | Solution |
|---|---|
| Missing values encoded as `?` | Replaced with `NaN`, then median/mode imputation |
| 18.4% missing in `normalized-losses` | Median imputation to retain all rows |
| Ordinal vs nominal categoricals | Integer mapping for cylinders; LabelEncoder for others |
| Multicollinearity among engine features | Used Ridge/Lasso for linear models; tree models handle it natively |
| Feature scale differences | StandardScaler applied only to linear models |

---

## 🚀 How to Run

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Run the Analysis

```bash
python PRCP_1017_AutoPricePred.py
```

This will:
1. Load and clean the dataset
2. Generate EDA visualizations
3. Train all 6 regression models
4. Print model comparison results
5. Output feature importance chart

---

## 📈 Business Insights

- **Premium Tier:** Larger engines + higher horsepower justify premium pricing
- **Economy Tier:** Optimize city/highway MPG to compete in the economy segment
- **Body Style:** Convertibles and hardtops command higher prices
- **Brand Equity:** Brand (make) is a top categorical predictor — brand-building directly impacts achievable price

---

## 🛠 Tech Stack

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-1.3+-green?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.4+-red)

---
- **Target:** `price` — continuous variable ($5,118 – $45,400)
- **Brands covered:** 22 makes including BMW, Toyota, Honda, Mercedes-Benz, Porsche, and more
