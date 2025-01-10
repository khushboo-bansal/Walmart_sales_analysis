# Walmart_sales_analysis
Overview

This project involves creating and querying a database for Walmart sales data. The database provides insights into revenue, product performance, customer behavior, and more. Additionally, it includes a dashboard for visualizing key metrics and trends. The SQL scripts and dashboard allow you to:

1. Create and populate the sales table.

2. Perform various queries to analyze the data.

3. Visualize data insights through the dashboard.


Key Queries

1. Total Revenue

SELECT ROUND(SUM(total), 0) AS total_revenue FROM sales;

2. Total Quantity of Products Sold

SELECT SUM(quantity) AS total_quantity FROM sales;

3. Sales by City

SELECT city, ROUND(SUM(total), 2) AS total_sales
FROM sales
GROUP BY city
ORDER BY total_sales DESC;

4. Average Gross Income by Branch and City

SELECT ROUND(AVG(Gross_income), 3) AS avg_gross_income, branch, city
FROM sales 
GROUP BY branch, city
ORDER BY avg_gross_income DESC;

5. Product Line with Highest Revenue

SELECT product_line, ROUND(SUM(total), 2) AS total_sales
FROM sales 
GROUP BY product_line
ORDER BY total_sales DESC
LIMIT 1;

6. Revenue by Customer Type

SELECT Customer_type, ROUND(SUM(total), 2) AS total_sales
FROM sales 
GROUP BY Customer_type;

7. Revenue by Gender

SELECT Gender, ROUND(SUM(total), 2) AS total_sales
FROM sales 
GROUP BY Gender;

8. Monthly Sales

SELECT month_name, ROUND(SUM(total), 2) AS monthly_sales 
FROM sales 
GROUP BY month_name
ORDER BY monthly_sales DESC;

9. Weekend vs Weekday Sales

SELECT day, ROUND(SUM(total), 2) AS day_sales
FROM sales
GROUP BY day
ORDER BY day_sales DESC;

Dashboard

The dashboard provides visual insights into:

1. Revenue Trends: Monthly, weekly, and daily revenue breakdowns.

2. Product Performance: Sales and quantity data for each product line.

3. Customer Insights: Analysis by customer type, gender.

4. Geographical Insights: Revenue and gross income by city and branch.


