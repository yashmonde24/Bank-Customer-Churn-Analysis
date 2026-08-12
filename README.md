## Bank Customer Churn Analysis - EDA Project

## What is this project about?
  This project looks at why bank customers leave the bank. I used data to find
  patterns, quantify churn risk across customer segments, and understand what
  makes a customer more likely to leave.


##  Dataset:
- 10,000 customer records
- 14 columns with customer details
- Source: Churn Modelling Dataset (Kaggle)

## Tools Used:
- Python
- Pandas
- Matplotlib
- Seaborn
- Jupyter Notebook

## What I did:
Loaded and cleaned the data
Removed columns that were not useful
Created charts to explore patterns across age, geography, product count,
and activity status
Calculated actual churn rate for each customer segment using groupby
analysis - not just visual patterns
Built a correlation heatmap and compared it against the segment-level
findings to check where a simple correlation was misleading

## Key Findings:
1. Overall churn rate: 20.4%.
2. Product count is the strongest churn driver. Churn rate rises sharply for customers with 3+ products - 82.7% (n=266) and 100% (n=60) churn,
   versus 7.6-27.7% for customers with 1-2 products (n=9,674).
   This pattern is non-linear, so it barely shows up in the correlation heatmap
   (NumOfProducts-Exited correlation is close to 0) - segment-level analysis
    was needed to catch it, since a straight-line correlation misses it entirely.
4. Geography: Germany-based customers churn at 32.4%, roughly double France and Spain (~16%).
5. Activity status: Inactive members churn at 26.9% vs 14.3% for active members.
6. Gender: Female customers churn at 25.1% vs 16.5% for male customers.
7. Age: churn rises steadily with age and peaks in the 51-60 group at 56%, consistent with Age showing the strongest linear correlation with churn
   among all numeric features (0.3).
8. Credit score: shows no meaningful correlation with churn (~0.0) - this is one factor that genuinely does not predict churn in this dataset.

# Recommendations
1. Focus on 2 product customers — customers with 2 products have the lowest churn. The bank should encourage 1 product customers to add a second product.
2. Investigate Germany separately — Germany has 2x higher churn than France and Spain. The bank should look into customer complaints and service quality specific     to Germany.
3. Re-engage inactive customers — inactive customers churn at nearly double the rate. The bank should reach out to inactive customers with offers or reminders        before they leave.
4. Pay attention to the 51-60 age group — this age group has the highest churn at 56%. The bank should create products or services that better suit this age group.

## Project Structure:
- Churn_Modelling.csv       # Dataset
- analysis.ipynb            # Jupyter Notebook with full analysis
- README.md                 # Project description

## What I Learned:
- How to clean and explore a real dataset
- How to create charts using Matplotlib and Seaborn
- How to quantify findings with groupby analysis instead of relying on
  visual patterns alone
- How correlation can hide a real, strong relationship when that
  relationship is non-linear - and why segment-level analysis matters
- The importance of checking sample size before trusting a segment-level
  finding, especially for small groups

  Insights Preview :
  - Visualization : https://github.com/yashmonde24/Bank-Customer-Churn-Analysis/tree/main/outputs/OUTCOMES
