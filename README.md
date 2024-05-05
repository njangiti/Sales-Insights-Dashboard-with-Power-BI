# Sales-Insights-Dashboard-with-Power-BI

### Overview

This repository contains a Power BI dashboard showcasing sales insights for Atliq Company. The dashboard provides a comprehensive view of revenue and sales quantity across different markets, along with top customers and products contributing to revenue.

### Features
#### Revenue by Market:
Visualizes the revenue generated in each market, providing insights into geographical performance.
#### Sales Quantity by Market:
Displays the sales quantity metrics, enabling analysis of market demand.
#### Top 5 Customers by Revenue: 
Highlights the top revenue-generating customers, aiding in customer relationship management strategies.
#### Top 5 Products by Revenue:
Identifies the best-performing products in terms of revenue, guiding product management decisions.

## Getting Started

### Prerequisites
Power BI Desktop installed on your system.

### Data Analysis Using SQL

1. Show all customer records

  `SELECT * FROM customers;`

2. Show total number of customers

  `SELECT count(*) FROM customers;`

3. Show transactions for Chennai market (market code for chennai is Mark001

  `SELECT * FROM transactions where market_code='Mark001';`

4. Show distrinct product codes that were sold in chennai

  `SELECT distinct product_code FROM transactions where market_code='Mark001';`

5. Show transactions where currency is US dollars

  `SELECT * from transactions where currency="USD"`

6. Show transactions in 2020 join by date table

  `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

7. Show total revenue in year 2020,

  `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`

8. Show total revenue in year 2020, January Month,

  `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

9. Show total revenue in year 2020 in Chennai

  `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";`

  Data Analysis Using Power BI
============================

  1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`





### Contributing
Contributions are welcome! If you have any suggestions, enhancements, or bug fixes, feel free to open an issue or create a pull request.


### Acknowledgements

Special thanks to Atliq Company for providing the dataset used in this dashboard.

