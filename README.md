# 🏅 Predicting Olympic Medal Performance Using Socio-Economic Indicators

This project explores how socio-economic and environmental indicators impact a country's performance at the Summer Olympics. By applying machine learning techniques, we developed a predictive model to estimate Olympic medal counts using publicly available development metrics.

---

## 🎯 Problem Statement

Can a country’s socio-economic and environmental indicators serve as reliable predictors of its Olympic medal performance?

---

## 📌 Key Objectives

- Merge diverse datasets (Olympic records, GDP, HDI, healthcare indicators).
- Identify key features influencing Olympic performance.
- Apply ML models to predict medal success.
- Interpret model outcomes to guide data-driven policy decisions.

---

## 🧱 Project Pipeline

### 1️⃣ Data Acquisition
- **Olympic Medal Data**: Gigasheet
- **Socio-Economic Data**: World Bank (GDP), UNDP (HDI, MYS, EYS, Life Expectancy)
- **Health Metrics**: NCD-RisC (BMI, Blood Pressure, Cholesterol, Diabetes)
- **Environmental Indicators**: CO₂ emissions, Maternal Mortality Rate (MMR)

### 2️⃣ Data Preprocessing
- ISO country code matching for dataset consistency.
- Imputation of missing values using mean/median strategies.
- Created new features: 
  - `Weighted Medal Score = Gold×3 + Silver×2 + Bronze×1`
  - `Medals per GDP`, `Medals per Capita`
- Robust Scaling and normalization to handle skewness and outliers.

### 3️⃣ Exploratory Data Analysis (EDA)
- Statistical summaries & correlation heatmaps.
- Cluster profiles based on socio-economic groupings.
- Visual trends for features like GDP, height, and health vs. medal counts.

### 4️⃣ Feature Engineering
- PCA analysis to identify dominant features.
- SHAP & feature importance to interpret ML predictions.

### 5️⃣ Machine Learning Models
| Model            | R² Score | RMSE   |
|------------------|----------|--------|
| LightGBM         | **0.895** | 25.95  |
| XGBoost          | 0.729    | 53.46  |
| CatBoost         | 0.673    | 21.74  |
| ElasticNet       | 0.564    | 54.35  |
| Random Forest    | 0.530    | 55.14  |
| Neural Networks  | 0.143    | 35.60  |

**🔍 Best Model:** LightGBM — Explains 89.5% of the variance in Olympic performance.

### 6️⃣ Clustering
- Applied **K-Means** and **Agglomerative Clustering** (best silhouette score for K=3).
- Clustered countries into:
  - High performers (high HDI, medals, GDP)
  - Developing nations (emerging performance)
  - Low-income, low-medal nations

---

## 📊 Key Insights

- **Education** (Mean & Expected Years of Schooling) > **GDP** in predicting Olympic success.
- **Healthcare and sustainability** (PHDI, CO₂ emissions) showed moderate influence.
- Clustered countries reflect disparities in development and performance.


