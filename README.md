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

## Assumptions
```python 
monthly_revenue = 40
annual_growth = 0.03
annual_discount_rate = 0.1
monthly_discount_rate = (1+annual_discount_rate)**(1/12)-1
cost_service = 0.15*monthly_revenue
marketing_cost = 0.05*monthly_revenue
nr_years = 8
```
