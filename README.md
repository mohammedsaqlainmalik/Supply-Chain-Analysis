# Supply-Chain-Analysis

# Delivery Delay & Profit Analysis: 
- The Business Question is Do late deliveries measurably hurt profitability ? and how much of total profit is at risk ? when orders slip past their scheduled shipping window?
# Dataset Source: 
- DataCo Supply Chain Dataset (Kaggle) 180,519 orders, 53 columns → cleaned to 172,765 rows, 20 columns
## Approach
- Cleaning: dropped 32 columns (which were fully redundant, or single-value fields — e.g. customer names/emails, zip codes, lat/long, IDs with no analytical value).
- Removed cancelled orders since they don't reflect real delivery time behavior.
- Feature engineering: Order Processing Time = shipping date − order date,Delay = processing time − scheduled shipment days ,Is_Delayed = Delay > 0, Profitability Flag = Profit / Loss / Break-even based on Order Profit Per Order
# Analysis: 
- KPI summary (on-time %, late %, total profit, profit lost todelayed orders), then profit and order-count aggregated by delayday bucket. Key Findings 54.7% of orders were delivered late — on-time delivery is 45.3%. Total profit across all orders: ~$7.5M Profit tied to delayed orders: ~$2.1M Profit per order doesn't collapse linearly with delay — mean profit per order stays in the $20–23 range across delay buckets from -2 to +4 days, meaning delay length alone isn't the strongest profit driver in this cut of the data. (This is a finding, not yet an explanation)
## Tools :
- Python(pandas, numpy, matplotlib, seaborn)
### Limitations:
- Next Steps No breakdown by Shipping Mode , Order Region , or Category Name yet — this is the natural next cut and likely where the real "supply chain" story is (e.g. which shipping mode or region drives the delay rate). No statistical test (e.g. t-test) behind the "delay doesn't hurt mean profit much" observation — currently descriptive only.

# preview:
![Alt text](https://github.com/mohammedsaqlainmalik/Supply-Chain-Analysis/blob/main/Profitibility_chart.png)
![Alt text](https://github.com/mohammedsaqlainmalik/Supply-Chain-Analysis/blob/main/delay%20vs%20mean_profit.png)
