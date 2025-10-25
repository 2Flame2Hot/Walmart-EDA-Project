# Walmart Sales Forecasting Project 🛒📈

## Overview
This project analyzes Walmart’s weekly sales data and builds forecasting models to identify key sales drivers, trends, and seasonality.  
The workflow includes **Exploratory Data Analysis (EDA)**, **Feature Engineering**, **Model Baseline**, and **Model Improvement (Hyperparameter Tuning)** using XGBoost.  

The project is designed as a **portfolio piece** to demonstrate skills in  
**Python, Pandas, Data Visualization, Machine Learning, and Model Optimization.**




```

## Project Structure

Walmart-Sales-EDA/
│
├── data/ # Raw & processed datasets (not uploaded if large)
│
├── notebooks/ # Jupyter Notebooks
│ ├── Analysis_Walmart_EDA.ipynb
│ ├── Feature_Engineering.ipynb
│ ├── Model_Baseline.ipynb
│ └── Model_Tuning_XGBoost.ipynb
│
├── reports/ # Exported HTML reports
│ ├── Analysis_Walmart_EDA.html
│ ├── Feature_Engineering.html
│ ├── Model_Baseline.html
│ └── Model_Tuning_XGBoost.html
│
├── reports/artifacts/ # Charts and summary tables
│ ├── feature_importance_top15.png
│ ├── per_store_mape_top10.png
│ ├── per_store_mape_bottom10.png
│ └── model_improvement_summary.json
│
└── README.md


```

## Workflow

### 1️⃣ Exploratory Data Analysis (EDA)
- Analyzed seasonal sales trends and top-performing stores  
- Compared **holiday vs. non-holiday weeks**  
- Examined correlations with external variables — *Fuel Price, CPI, and Unemployment Rate*  
- Identified patterns and anomalies using line plots and heatmaps  

📊 **Report:** [`Analysis_Walmart_EDA.html`](reports/Analysis_Walmart_EDA.html)

---

### 2️⃣ Feature Engineering
- Converted `Date` into temporal components: `Year`, `Month`, `Week`, `Quarter`, `DayOfWeek`  
- Added cyclical seasonality: `Month_sin`, `Month_cos`, and `Peak_Season_Flag`  
- Generated lag & rolling features: `Weekly_Sales_Real_lag1`, `rollmean8`, etc.  
- Adjusted for inflation (CPI) to compute `Weekly_Sales_Real`  
- Created target variable `Target_next_week` for one-step-ahead forecasting  

📊 **Report:** [`Feature_Engineering.html`](reports/Feature_Engineering.html)

---

### 3️⃣ Baseline Model (XGBoost)
- Built an **XGBoost Regressor** using default parameters  
- Time-based train/test split: Train = 2010–2011, Test = 2012  
- Evaluation metrics:
  - **RMSE:** ~97,804  
  - **MAPE:** ~6.40%  
- Feature importance: `Store_avg_to_date`, `Weekly_Sales_Real_rollmean8`, `Weekly_Sales_Real_rollmean4`  

📊 **Report:** [`Model_Baseline.html`](reports/Model_Baseline.html)

---

### 4️⃣ Model Improvement (Hyperparameter Tuning)
- Tuned **XGBoost** using `GridSearchCV` with `TimeSeriesSplit (n_splits=5)`  
- Evaluated multiple parameters:
  - `max_depth`, `learning_rate`, `n_estimators`, `subsample`, `colsample_bytree`
- Compared tuned XGBoost with **RandomForest** and **LightGBM**
- Performed **Bias Analysis** (MAPE by Month & Holiday Period)
- Exported charts and tables for GitHub reports

📊 **Report:** [`Model_Tuning_XGBoost.html`](reports/Model_Tuning_XGBoost.html)

---

## 📈 Model Performance Summary

| Model | RMSE | MAPE | Notes |
|-------|------|------|-------|
| **Baseline XGBoost** | 97,804 | 6.40% | Default parameters |
| **Tuned XGBoost** | 100,362 | 6.06% | Improved % accuracy, slight RMSE increase |

**Key Findings:**
- MAPE improved by ~0.34 percentage points  
- RMSE increased slightly due to variance from deeper trees  
- Model performs well on average but underperforms during **holidays / peak seasons**  
- Top drivers: `Store_avg_to_date`, `Weekly_Sales_Real_rollmean8`, `CPI_lag1`

---

## 🧠 Business Insights
- Stores with strong cumulative performance and consistent momentum tend to forecast better  
- Economic factors like **CPI** and **Fuel Price** influence weekly sales levels  
- Model accuracy drops slightly during high-demand months (January & November)  
  → Suggests need for holiday-aware features and retraining around promotions  

---

## 🧾 Next Steps
- Expand hyperparameter search (e.g., `min_child_weight`, `gamma`, `reg_lambda`)  
- Add **holiday-aware** and **promotion-based** features  
- Apply **cross-validation with more folds** for stability  
- Segment models by **store cluster** or **region**  
- Create a **Tableau / Power BI dashboard** for interactive insights  

---

## 🧰 Tools & Technologies
- **Language:** Python  
- **Libraries:** Pandas, NumPy, Scikit-learn, XGBoost, LightGBM, Matplotlib  
- **Environment:** JupyterLab / Anaconda  
- **Visualization:** Matplotlib, Seaborn  
- **Version Control:** Git & GitHub  

---

## 👤 Author
**Siripaiboon Janpetch**  
🎓 M.S. Data Analytics @ The University of Texas at San Antonio  
📍 Focus: Business Analytics, Forecasting, and Data Science for Retail  
🔗 [LinkedIn](https://www.linkedin.com/in/siripaiboon-janpetch) | [GitHub](https://github.com/2Flame2Hot)
