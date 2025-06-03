## Sales-Trend-Analysis-Using-Aggregations


## Task Overview

This task focuses on analyzing monthly revenue and order volume using SQL in PostgreSQL.
It demonstrates data grouping, aggregation, and time-based trend analysis using a dataset.

##  Objective

To extract insights from sales data by:
- Grouping orders by month and year
- Calculating monthly revenue SUM(amount)
- Counting monthly order volume COUNT(DISTINCT order_id)

##  Dataset

**Table Name:** online_sales.orders  
Columns:
- order_id (SERIAL, Primary Key)
- order_date (DATE)
- amount (NUMERIC)
- product_id (INT)

Sample dataset is available in:  
Sales_Trend_Sample_Data.xlsx

##  Tools Used

PostgreSQL (via pgAdmin)
- SQL
- Microsoft Excel (for data file)
- MS Word / PDF for documentation
- GitHub
  
##  SQL Steps Performed

1. **Create Schema and Table**
2. **Insert Sample Data**
3. **Run Analysis Query**:

sql
SELECT
    EXTRACT(YEAR FROM order_date) AS year,
    EXTRACT(MONTH FROM order_date) AS month,
    COUNT(DISTINCT order_id) AS total_orders,
    SUM(amount) AS total_revenue
FROM
    online_sales.orders
WHERE
    order_date BETWEEN '2022-01-01' AND '2022-12-31'
GROUP BY
    EXTRACT(YEAR FROM order_date),
    EXTRACT(MONTH FROM order_date)
ORDER BY
    year,
    month;


## Result Snap

 Output (Result Table)
| Year | Month | Total Orders | Total Revenue |
|------|-------|--------------|----------------|
| 2022 | 1     | 2            | 700.50         |
| 2022 | 2     | 2            | 500.00         |
| 2022 | 3     | 2            | 800.75         |
| 2022 | 4     | 2            | 475.25         |
| 2022 | 5     | 2            | 250.00         |
| 2022 | 6     | 2            | 350.00         |
| 2022 | 7     | 1            | 375.00         |
| 2022 | 8     | 1            | 415.00         |
| 2022 | 9     | 1            | 295.00         |
| 2022 | 10    | 1            | 500.00         |
| 2022 | 11    | 1            | 600.00         |
| 2022 | 12    | 1            | 700.00         |


## What I Learned

- Using EXTRACT() to group by time (year/month)
- Aggregating sales using SUM() and COUNT()
- Writing clean and efficient SQL queries for reporting
- Creating data-driven insights from raw transaction data
- Documenting SQL tasks in a professional format
