# Customer-Lifetime-Value-Analysis-Door-Bell


## Overview:
The Door Bell CLV Analyzer is a Python project aimed at assessing the customer lifetime value (CLV) for Door Bell, Inc. The project focuses on understanding the impact of autopay on customer retention and provides insights crucial for strategic marketing decisions.

## Objectives:
- Analyze historical data to calculate CLV for customers with and without autopay.
- Determine the potential value of converting existing customers to autopay.
- Provide actionable insights for marketing strategies aimed at improving customer retention.

## Features:
- CLV calculation for autopay and non-autopay customers.
- Visualization of CLV trends over time.
- Analysis of retention rates for autopay and non-autopay customers.

## Technology Stack:
- Python
- Jupyter Notebook
- Pandas
- Matplotlib

## Data:
The data used in this project was fabricated for the sake of analysis. It includes annual churn rates for autopay and non-autopay customers over an 8-year period.

## Assumptions:
```python 
monthly_revenue = 40
annual_growth = 0.03
annual_discount_rate = 0.1
monthly_discount_rate = (1+annual_discount_rate)**(1/12)-1
cost_service = 0.15*monthly_revenue
marketing_cost = 0.05*monthly_revenue
nr_years = 8
```
## Insights: 
- Calculate CLV for autopay and non-autopay customers
```python 
revenues_ap = array1
service_ap = 0.15*revenues_ap
marketing_ap = 0.05*revenues_ap
profit_ap = revenues_ap - service_ap - marketing_ap
expected_profit_ap = retention_ap * profit_ap

pv_expected_profit_ap = np.ones(96,)
for i in range(len(expected_profit_ap)):
    pv_expected_profit_ap[i] = expected_profit_ap[i]/(1+monthly_discount_rate)**(i+1)


pv_expected_profit_ap = pv_expected_profit_ap# present value of expected profits
clv_ap = np.cumsum(pv_expected_profit_ap)
```
CLV for AutoPay Users: **1803.660201** | CLV for Non-AutoPay Users: **1553.722933**
