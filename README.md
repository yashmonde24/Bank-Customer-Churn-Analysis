# Customer Churn Patterns in Banking — An Exploratory Study

# 1. Background and Overview

Banks lose customers every year. The real problem is they often don't know which customers are about to leave or why.

This project digs into 10,000 bank customer records to find out what kind of customers are most likely to leave. Instead of just making charts, I calculated the actual churn rate for each customer group to find where the real risk is sitting.

Tools: Python, Pandas, Matplotlib, Seaborn, Jupyter Notebook

Problem Statement :
A bank is losing 1 in 5 customers with no clear understanding of who is leaving or why.   This project uses customer data to identify which groups are at the highest risk of leaving so the bank knows where to focus its retention efforts.

Objective  :
 - Calculate the actual churn rate across customer segments — age, geography, gender,         product count, and activity status.
 - Identify which factors have the strongest link to churn.
 - Provide a clear, data-backed starting point for retention decisions.

# 2. Data Structure Overview

Source	Kaggle — Churn Modelling Dataset
Rows	10,000 customer records
Columns	14 (11 used after cleaning)
Target Column	Exited (1 = Churned, 0 = Stayed)

Columns Removed
- RowNumber — just an index
- CustomerID — no analytical value
- Surname — personal info, not useful

No missing values found — no rows were dropped during cleaning

# 3. Executive Summary

Overall churn rate: 20.37% — meaning 1 in 5 customers left the bank. Overall retention rate: 79.63%

Four factors stand out as the strongest reasons customers leave:
- Product count — customers with 3+ products churn at 83–100%
- Age — the 51–60 age group has a 56% churn rate
- Geography — Germany churns at double the rate of France and Spain
- Activity status — inactive customers churn at nearly 2x the rate of active ones

One factor that does not matter: Credit Score — it has zero relationship with whether a customer stays or leaves.

# 4. Insights Deep Dive

- Product Count — Strongest Signal

  - 1 product → 27.7% churn (5084 customers) 
  - 2 products → 7.6% churn (lowest — the sweet spot, 4590 customers) 
  - 3 products → 82.7% churn (266 customers)
  - 4 products → 100% churn (60 customers)

This pattern does not show up in a standard correlation check because it is not a straight-line relationship. Segment-level groupby analysis was needed to catch it.

- Age — Steady Rise, Sharp Peak

 - 18–30 → 8% churn
 - 31–40 → 12% churn
 - 41–50 → 34% churn
 - 51–60 → 56% churn
 - 60+ → 25% churn

Churn builds steadily with age and peaks hard in the 51–60 bracket. Age also has the strongest straight-line correlation with churn (0.3) among all numeric columns.
  
- Geography — Germany Is an Outlier

  - Germany → 32.4% churn
  - France → 16.1% churn
  - Spain → 16.7% churn

Germany is losing customers at double the rate. The data does not explain why — this needs a separate investigation.

- Activity Status — Engagement Matters

  - Inactive members → 26.9% churn
  - Active members → 14.3% churn

Customers who stop engaging with the bank are nearly twice as likely to leave.

- Gender

  Female → 25.1% churn
  Male → 16.5% churn
  
A clear gap exists. The data does not tell us why.

- Credit Score — No Signal

  - Correlation with churn: ~0.0
  - Credit score tells us nothing about whether a customer will leave

## 5. Recommendations

- Push 1-product customers to 2 products — 2-product customers have the lowest churn at 7.6%. A targeted cross-sell campaign here is the easiest win.

- Investigate Germany separately — a 32% churn rate versus 16% everywhere else is too large to ignore. Customer complaints, service gaps and local competition all need to be looked at.
  
- Catch inactive customers early — by the time someone goes inactive, they are already halfway out the door. Reach out before they decide to leave.
  
- Build something for the 51–60 age group — more than half of this group is leaving. Products or communication designed for this age group could make a real dent.

# 6. Assumptions and Limitations
- Dataset is from Kaggle — may not reflect a real bank's actual customer base.
- 3-product (n=266) and 4-product (n=60) segments are small — findings should be validated with more data.
- The data shows patterns but not reasons — we cannot confirm what caused customers to leave.
- Germany's high churn could be a data issue, not a real market problem.

## 7. Future Enhancements
- Build a machine learning model to predict which customer is likely to leave next.
- Add complaint and transaction data to understand the reasons behind churn.
- Run a deeper analysis on Germany separately.
- Track churn over time to see if these patterns hold.

## 8. Deliverables
File	Description
- Churn_Modelling.csv	Raw dataset
- analysis.ipynb	Full analysis with charts and findings
- README.md	Project documentation

## 9. Outcomes Preview :
  - EDA Visualization : https://github.com/yashmonde24/Bank-Customer-Churn-Analysis/tree/main/outputs/OUTCOMES
