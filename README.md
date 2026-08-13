## Bank Customer Churn Analysis — EDA Project

## 1. Background and Overview

Every bank loses customers. The real problem is not knowing which customers are about to leave and why.

This project analyzes 10,000 bank customer records to find out what makes a customer more likely to leave. The goal was to go beyond surface-level charts and actually quantify churn risk across different customer segments.

Tool Used: Python (Pandas, Matplotlib, Seaborn) in Jupyter Notebook

## 2. Data Structure Overview
Detail	Info

Source	Kaggle — Churn Modelling Dataset
Rows	10,000 customer records
Columns	14 (11 used after cleaning)
Target Column	Exited (1 = Churned, 0 = Stayed)

Columns Removed

RowNumber — just an index
CustomerID — no analytical value
Surname — personal info, not useful

## 3. Executive Summary

The overall churn rate in this dataset is 20.4% — meaning 1 in 5 customers left the bank.

After analyzing all customer segments, 4 factors stand out as the strongest drivers of churn:

Product Count — strongest signal. Customers with 3+ products churn at 83–100%
Age — churn peaks sharply in the 51–60 age group at 56%
Geography — Germany churns at 2x the rate of France and Spain
Activity Status — inactive customers churn at nearly double the rate of active ones

One surprising finding: Credit Score has zero impact on churn. Despite being a common banking metric, it showed no meaningful relationship with whether a customer left or stayed.

## 4. Insights Deep Dive

- Product Count — Strongest Churn Signal

  1 product → 27.7% churn
  2 products → 7.6% churn (lowest — sweet spot)
  3 products → 82.7% churn (n=266)
  4 products → 100% churn (n=60)
  
  This pattern is non-linear. It does not show up in the correlation heatmap because a straight-line correlation completely misses it. Segment-level analysis was needed to catch this.

- Age — Steady Rise With a Clear Peak

  Churn rises steadily with age
  Peaks at 51–60 age group → 56% churn
  Age has the strongest linear correlation with churn among all numeric features (0.3)
  
- Geography — Germany Is an Outlier
  
  Germany → 32.4% churn
  France → ~16% churn
  Spain → ~16% churn

  Germany churns at roughly double the rate of the other two countries. The data does not explain why — this needs further investigation.

- Activity Status — Engagement Matters

  Inactive members → 26.9% churn
  Active members → 14.3% churn
  
  Customers who are not engaging with the bank are nearly twice as likely to leave.

- Gender

  Female → 25.1% churn
  Male → 16.5% churn
  
  A real gap exists but the reason behind it is unclear from this data alone.

- Credit Score — No Signal

  Correlation with churn: ~0.0
  This is one factor that genuinely does not predict churn in this dataset

## 5. Recommendations

- Push customers from 1 product to 2 products Customers with 2 products have the lowest churn at 7.6%. A simple cross-sell campaign targeting 1-product customers    could meaningfully reduce churn.

- Investigate Germany urgently Germany's churn rate is double other markets. This needs a separate deep dive — customer complaints, service quality, and             competitor activity in that market should all be looked at.

- Re-engage inactive customers early Inactive customers churn at nearly 2x the rate. The bank should identify inactive customers early and reach out with offers     or check-ins before they decide to leave.

- Build retention programs for the 51–60 age group This group churns at 56%. Products and communication designed specifically for this age group could reduce that   number significantly.

# 6. Assumptions and Limitations
- The dataset is from Kaggle and may not reflect a real bank's actual customer base
- Sample sizes for 3-product (n=266) and 4-product (n=60) segments are small — findings should be validated with more data before acting on them
- The data does not include reasons why customers left — so we can find patterns but cannot confirm causes
- Germany's high churn rate could be a data collection issue, not a real market difference

## 7. Future Enhancements
- Build a machine learning model to predict which individual customer is likely to churn next
- Add customer complaint and transaction data to understand the reason behind churn, not just the pattern
- Separate Germany data into its own analysis to dig deeper into what is driving the difference
- Track churn over time to see if these patterns are consistent or changing

## 8. Deliverables
File	Description
Churn_Modelling.csv	Raw dataset
analysis.ipynb	Full analysis with charts and findings
README.md	Project documentation

## 9. Outcomes Preview :
  - EDA Visualization : https://github.com/yashmonde24/Bank-Customer-Churn-Analysis/tree/main/outputs/OUTCOMES
