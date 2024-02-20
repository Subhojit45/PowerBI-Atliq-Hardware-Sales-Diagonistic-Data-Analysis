# 📊Atliq Hardware Sales Insights Data Analysis Project 📊

## 📌Code Snippets:

## ⚙ Data Analysis Using SQL:
 
### For Show all customer records:

`SELECT * FROM customers;`

### For Show total number of customers:

`SELECT count(*) FROM customers;`

### For Show transactions for Chennai market (market code for chennai is Mark001

`SELECT * FROM transactions where market_code='Mark001';`

### For Show distrinct product codes that were sold in chennai

`SELECT distinct product_code FROM transactions where market_code='Mark001';`

### For Show transactions where currency is US dollars

`SELECT * from transactions where currency="USD";`

### For Show transactions in 2020 join by date table

`SELECT transactions. date FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

### For Show total revenue in year 2020

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`

### For Show total revenue in year 2020, January Month

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

### For Show total revenue in year 2020 in Chennai

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";`

## ⚙ Data Analysis Using Power BI Formula to

## 📌create Converted_INR

 `column=Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)"` then [sales_amount]*75 else [sales_amount], type any)
