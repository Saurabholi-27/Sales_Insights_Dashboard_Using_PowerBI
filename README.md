
# Sales Insights Dashboard Using PowerBI and PowerQuery

This project showcases the use of Power Query and DAX Query to analyze sales data, add new measures and columns, and create a dashboard using Power BI. The goal is to provide insights into sales patterns and identify areas for improvement for HR.

# Tools Used
 - MySQl Workbench
 - Power BI
 - Power Query
 - Dax Query
 - Data modeling

# Instructions to setup mysql on your local computer
 - Follow step in this video to install mysql on your local computer https://www.youtube.com/watch?v=WuBcTJnIuzo

 - SQL database dump is in db_dump.sql file above. Download db_dump.sql file to your local computer and import it as per instructions given in the tutorial video


# Cleaning and Analysis Using SQL

1. Show all customer records
``` bash
  SELECT * FROM customers;
```
2. Show total number of customers
``` bash
  SELECT count(*) FROM customers;
```
3. Show transactions for Chennai market (market code for chennai is Mark001
``` bash
  SELECT * FROM transactions where market_code='Mark001';
```
4. Show distrinct product codes that were sold in chennai
``` bash
  SELECT distinct product_code FROM transactions where market_code='Mark001';
```
5. Show transactions where currency is US dollars
``` bash
  SELECT * from transactions where currency="USD"
```
6. Show transactions in 2020 join by date table
``` bash
  SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;
```
7. Show total revenue in year 2020,
``` bash
   SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";
```
8. Show total revenue in year 2020, January Month,
``` bash
  SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");
```
9. Show total revenue in year 2020 in Chennai
``` bash
  SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";
```
# Cleaning and Analyzing using Power Query

 - Use Power Query to clean and transform the data
 - Create a copy template for one sheet in Power Query transformations and apply the same transformations to all sheets
 - Apply all necessary cleaning steps, such as removing duplicates, renaming columns, and changing data types
 - Create a parameter to select the desired data based on a specific condition
 - Encapsulate all steps into a function to be reused for future sheets and data
 - Load and Apply the cleaned data into Power BI

# Exploring and Manipulate Some Data Using DAX Query
 - With DAX Query, we can effectively manipulate and analyze the data to provide insights for visulization and identify areas for improvement for HR.
 - Create Measures and columns Using DAX functions such as count, sum, calculate, if, switch, divide and Date-time function for exploring some clean data for improve dashboard KPI in PowerBI.

# Power BI Dashboard Visualization
 - Design the dashboard layout
 - Create a measure table to aggregate and display the data using Dax functions
 - Use Visulizations for charts and filters for filter dashboard
 - Add Month column as Slicer and add some informative KPI.
 - Add Card chart, Pie chart, Line chart, Table chart, Matrix chart, Area chart etc.

# Guidance

Huge thanks to Codebasic for the guidance in this wonderful project.
