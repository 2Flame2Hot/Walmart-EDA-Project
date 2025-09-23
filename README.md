# Walmart Sales Forecasting Project 🛒📈

## Overview
This project analyzes Walmart’s weekly sales data and builds forecasting models to identify key sales drivers, trends, and seasonality.  
The workflow includes **Exploratory Data Analysis (EDA)**, **Feature Engineering**, and a **Baseline Machine Learning Model** using XGBoost.  

The project is designed as a portfolio piece to demonstrate skills in **Python, Pandas, Data Visualization, and Machine Learning**.

---

## Project Structure
Walmart-Sales-EDA/
│
├── data/ # Dataset (local, not uploaded to GitHub if large)
│   │
│   └── Walmart_Store_sales.csv
│
│
├── notebooks/ # Jupyter Notebooks
│   │
│   ├── Analysis_Walmart_EDA.ipynb
│   │
│   ├── Feature_Engineering.ipynb
│   │
│   └── Model_Baseline.ipynb
│
│
├── reports/ # Exported HTML reports
│   │
│   ├── Analysis_Walmart_EDA.html
│   │
│   ├── Feature_Engineering.html
│   │  
│   └── Model_Baseline.html
│
│
└── README.md


---

## Workflow
### 1. Exploratory Data Analysis (EDA)
- Analyzed sales trends over time  
- Compared **holiday vs non-holiday weeks**  
- Correlation with external variables: *Fuel Price, CPI, Unemployment*  
- Visualized top-performing stores and seasonal sales patterns  

### 2. Feature Engineering
- Converted `Date` to datetime features (`Year`, `Month`, `Week`, `Quarter`, `DayOfWeek`)  
- Created cyclical seasonality features (`Month_sin`, `Month_cos`)  
- Generated lag and rolling window features (e.g., `lag1`, `roll8`) to capture historical patterns  

### 3. Baseline Model (XGBoost)
- Trained an **XGBoost Regressor**  
- Evaluation metrics:
  - **RMSE:** ~97,804  
  - **MAPE:** ~6.40%  
- Feature importance showed rolling averages and store-level averages were strong predictors  
- Visualization confirmed model captured overall trends but missed some extreme peaks  

---

## Results
- **Strong baseline model** capturing seasonality and store effects  
- Average prediction error around **6%**  
- Clear insights into how holidays and external factors impact sales  

---

## Next Steps
- Perform **Hyperparameter Tuning** for better accuracy  
- Use **Cross-Validation** instead of simple train-test split  
- Try alternative models (e.g., LightGBM, Prophet, LSTM)  
- Build an **Interactive Dashboard** in Tableau or Power BI for business users  

---

## Tools & Technologies
- **Languages:** Python (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, XGBoost)  
- **Environment:** JupyterLab / Jupyter Notebook  
- **Visualization:** Matplotlib, Seaborn  
- **Version Control:** Git & GitHub  

---

## Author
👤 Developed by Siripaiboon Janpetch 
🎓 MS Data Analytics Student @ UTSA  
🔗 [LinkedIn Profile](www.linkedin.com/in/siripaiboon-janpetch) | [GitHub Profile](https://github.com/2Flame2Hot)  

