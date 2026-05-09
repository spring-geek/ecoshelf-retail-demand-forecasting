# ecoshelf-retail-demand-forecasting
# 🌿 EcoShelf: Predicting Retail Demand to Minimize Food Waste

**Author:** Precious Ayoola  
**Track:** Data Science  
**Domain:** Business & Growth Analytics / Sustainability  
**Target Stakeholder:** Retail Operations Manager / Sustainability Lead

---

## 📌 Project Overview

Retailers globally lose billions of dollars annually due to the spoilage of perishable goods. The "Perishability Paradox" forces store managers to choose between:

- **Overstocking** → food waste, tied-up capital, financial loss
- **Understocking** → missed sales, customer dissatisfaction

**EcoShelf** tackles this problem by building a machine learning–driven demand forecasting model to help retailers optimize stock levels for high-risk perishable departments — reducing waste while protecting revenue.

---

## 🎯 Objectives

1. Analyze historical sales patterns of perishable goods
2. Identify the key factors influencing weekly demand
3. Build and evaluate a regression model to predict weekly sales
4. Simulate how improved demand prediction can reduce overstock-related waste

---

## 📂 Repository Structure

```
ecoshelf-retail-demand-forecasting/
│
├── README.md
├── notebooks/
│   ├── 01_ecoshelf_data_visualization.ipynb   # Exploratory Data Analysis & visualizations
│   └── 02_ecoshelf_ml_model.ipynb             # Feature engineering, modeling & evaluation
├── data/
│   └── data_source.md                         # Instructions to download the dataset
├── reports/
│   └── ecoshelf_project_proposal.pdf          # Full project report (Deliverable 4)
└── requirements.txt                           # Python dependencies
```

---

## 📊 Dataset

**Source:** [Walmart Recruiting – Store Sales Forecasting](https://www.kaggle.com/competitions/walmart-recruiting-store-sales-forecasting) via Kaggle

| Detail | Info |
|--------|------|
| Stores | 45 |
| Departments | 99 |
| Records | 140,000+ |
| Focus Departments | Dept 92 (Grocery) & Dept 95 (Produce) |

**Key Features Used:**
- Store, Department, Date, Weekly_Sales, IsHoliday
- Temperature, Fuel_Price, CPI, Unemployment
- Engineered: Week, Month, Store Size, High_Heat indicator

---

## 🔬 Methodology

### Notebook 1 — Data Visualization
- Exploratory Data Analysis (EDA)
- Sales trend analysis by department, store, and season
- Correlation analysis between external factors and demand
- Holiday vs. non-holiday demand comparison

### Notebook 2 — ML Modelling
- Feature engineering (seasonal indicators, economic variables)
- Baseline model: Seasonal historical weekly average
- Final model: **Random Forest Regressor**
- Evaluation: MAE, Weighted MAE (5x holiday weight), R²

---

## 📈 Results

| Model | MAE |
|-------|-----|
| Seasonal Baseline | 36,560 |
| Random Forest | **4,732** |

| Metric | Score |
|--------|-------|
| R² Score | **0.967** |
| Forecast Error Reduction | **87%** |
| Holiday-Weighted MAE (WMAE) | 5,803 |

> The Random Forest model reduced forecast error by approximately **31,827 units per week** compared to the traditional averaging baseline.

---

## 💡 Key Findings

- **Store Size** is the single most dominant predictor of weekly sales
- **Week of Year** is a strong seasonal driver
- Environmental factors (temperature, holiday flag) showed limited impact on total sales volume — suggesting sales are driven by structural store characteristics and seasonal cycles more than external conditions
- The model maintains strong performance even during high-risk holiday periods

---

## 💰 Financial & Sustainability Impact

Assuming an average perishable unit value of **$3**:

| Impact | Estimate |
|--------|----------|
| Weekly optimization potential | ~$95,000 |
| Annual precision improvement | ~$4.9 million |
| Conservative waste reduction (20–25%) | **$1M+ annually** |

Beyond financial savings, reduced overstocking directly lowers food waste and supports retailer sustainability goals.

---

## 🛠️ Tools & Libraries

- **Python** (Pandas, NumPy, scikit-learn)
- **Visualization:** Matplotlib, Seaborn
- **Modelling:** Random Forest Regressor, Linear Regression
- **Environment:** Jupyter Notebook

---

## ⚙️ How to Run

1. Clone this repository:
```bash
git clone https://github.com/spring-geek/ecoshelf-retail-demand-forecasting.git
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Download the dataset from [Kaggle](https://www.kaggle.com/competitions/walmart-recruiting-store-sales-forecasting) and place files in the `data/` folder

4. Run the notebooks in order:
   - Start with `01_ecoshelf_data_visualization.ipynb`
   - Then run `02_ecoshelf_ml_model.ipynb`

---

## ⚠️ Limitations

- Dataset does not contain direct food waste measurements — waste reduction is estimated from forecast improvement
- Model predicts sales volume, not spoilage quantity
- Environmental variables showed limited impact on total sales in this dataset
- Results may not generalise to all retail environments

---

## 🔮 Future Work

- Incorporate real waste tracking data to directly quantify sustainability impact
- Test on real-time operational retail data
- Explore time-series models (e.g. XGBoost, LSTM) for further accuracy improvement
- Extend analysis to additional perishable departments

---

## 📄 License

This project was completed as part of the AltSchool Africa Data Science programme (Baraka 2025 Cohort).  
Dataset credit: Walmart / Kaggle.
