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
```python 
churn = pd.DataFrame(
    {
        "autopay": [0,0.070, 0.097, 0.103, 0.095, 0.078, 0.069, 0.059],
        "no_autopay": [0,0.122, 0.162, 0.154, 0.134, 0.120, 0.111, 0.096],
    }
)
```

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
> [!NOTE]  
> CLV for AutoPay Users: **$1803.660201** | CLV for Non-AutoPay Users: **$1553.722933**


- Visualization of CLV trends over time
```python 
# created a single plot with 2-lines
a = plt.plot(homealarm["no_autopay"], label="No-Autopay")
a = plt.plot(homealarm["autopay"], label="Autopay")
plt.legend()
```
<p align="center">
  <img width="460" height="300" src="https://github.com/arnavv-agarwal/Customer-Lifetime-Value-Analysis-Door-Bell/blob/main/CLVAP.png">
</p>

- Analysis of retention rates for autopay and non-autopay customers.
```python 
# created a single plot with 2-lines
b = plt.plot(retention_ap, label="Autopay")
b = plt.plot(retention_nap, label="No-Autopay")
plt.legend()
```
<p align="center">
  <img width="460" height="300" src="https://github.com/arnavv-agarwal/Customer-Lifetime-Value-Analysis-Door-Bell/blob/main/CLVR.png">
</p>

- Calculate the maximum amount to spend on autopay incentives
```python 
max_pay = homealarm["autopay"][95] - homealarm["no_autopay"][95]
print(f"Maxium amount to spend on autopay incentives is {max_pay.round(2)}")
```

> [!NOTE]  
> Maxium amount to spend on autopay incentives is $249.94

## Suggested marketing actions

- <p align="justify">Door Bell can offer free 30 USD worth of days in its subscription for non-autopay customers who switch to autopay cutomers. For every year they complete under the autopay contract, they will recieve suitable number of days free corresponding to the dollar value of 30 USD. This strategy will help us in convincing the non-autopay customers to switch to autopay customers and also help us in retaining them. The total cost for this marketing campaign will come around to be (30 X 8) = 240 USD, which is less then the autopay incentives.</p>

- <p align="justify">Door Bell can also offer special priviledges to autopay customers which can cost less that 249.94 USD. For instance, Door Bell can offer an additional feature into its alarm system which can may offer its client 24/7 survilliece by the employyes of Door Bell. This gives additional security to its users. This additional feature might be able to convince non-autopay customer to switch to autopay customers.</p>
