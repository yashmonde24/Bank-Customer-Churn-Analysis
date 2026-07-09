# Bank Customer Churn Analysis -EDA Project

## What is this project about?
This project looks at why bank customers leave the bank. We use data to find patterns and understand what makes a customer more likely to leave.

---

## Dataset
- 10,000 customer records
- 14 columns with customer details
- Source: Churn Modelling Dataset (Kaggle)

---

## Tools Used
- Python
- Pandas
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## What I did
1. Loaded and cleaned the data
2. Removed columns that were not useful
3. Created charts to understand the data better
4. Found key reasons why customers leave

---
## Key Findings
- Overall churn rate: 20.4%
- Churn rate spikes sharply for customers with 3+ products — 82.7% (n=266) 
  and 100% (n=60) churn, vs 7.6-27.7% for customers with 1-2 products (n=9,674).
  Note: this relationship is non-linear, so it does not show up as a strong
  correlation in the heatmap (NumOfProducts-Exited correlation ≈ 0.0) — 
  segment-level analysis was needed to catch it.
- Germany-based customers churn at 32.4%, roughly double France and Spain (~16%)
- Inactive members churn at 26.9% vs 14.3% for active members
- Female customers churn at 25.1% vs 16.5% for male customers
- Churn peaks in the 51-60 age group at 56%, consistent with Age showing the
  strongest linear correlation with churn among numeric features (0.3)
- Credit score showed no meaningful correlation with churn (≈ 0.0)

**Priority retention segments:** customers with 3+ products, inactive members, 
and Germany-based customers show the highest churn risk.

---

## Project Structure
```
├── Churn_Modelling.csv       # Dataset
├── analysis.ipynb           # Jupyter Notebook with full analysis
└── README.md                 # Project description
```

---

## How to Run
1. Download the repository
2. Open `analysis.ipynb` in Jupyter Notebook
3. Run all cells from top to bottom

---

## What I Learned
- How to clean and explore a real dataset
- How to create charts using Matplotlib and Seaborn
- How to find useful patterns in data
