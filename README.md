# Telco Customer Churn Analysis

Predicting which telecom customers are likely to churn, finding the root causes, and choosing the best cut-off for retention calls.

## Business question
Which customers are likely to leave, why, and who should the retention team call to get the best return?

## Dataset
Telco Customer Churn: 7,043 customers and 21 columns (contract, tenure, services, charges and whether the customer churned). Overall churn rate: *26.5%*.

## Files
- Teleco-Customer-Churn.ipynb: the full analysis notebook
- Teleco-Customer-Churn.html: the same notebook as a web page, easy to read without Jupyter

## What I did
1. *Load and clean:* converted TotalCharges from text to numbers and filled the 11 missing values with the median.
2. *Exploratory analysis:* compared churn by contract type, tenure and monthly charges.
3. *Preprocessing:* one-hot encoded the categorical columns (30 features) and scaled the numeric ones, fitting the scaler on training data only.
4. *Modelling:* trained Logistic Regression and Random Forest with an 80/20 split.
5. *Threshold modelling:* used the precision-recall trade-off and a profit estimate to pick the best call cut-off.

## Key findings
- *Contract type matters most:* month-to-month customers churn at 42.7%, one-year at 11.3% and two-year at 2.8%.
- *New customers leave first:* churn is 47.4% in the first 12 months of tenure and 9.5% after 49 months.
- *Fibre optic internet* is the strongest churn driver. Two-year contracts and longer tenure are the strongest reasons customers stay.
- *Models:* Logistic Regression ROC-AUC about 0.84 and Random Forest about 0.84.
- *Best cut-off:* about 0.25 under my assumptions, which gives high recall of churners at a profit above the default 0.50 cut-off.

## Assumptions
The profit estimate uses assumed figures: customer value saved of 500, call cost of 20 and a 30% save rate. These should be replaced with the company's real numbers.

## Tools
Python, pandas, NumPy, matplotlib, scikit-learn
