# Pizza Sales Data Analysis

## Objectives
This project aims to analyze pizza sales data to:
1. Calculate key performance indicators (KPIs) such as total revenue, average order value, and total quantity sold.
2. Identify trends in sales by time (daily and monthly) and category.
3. Determine the highest and lowest performing pizzas by revenue, quantity, and orders.
4. Provide actionable insights for improving business performance.

## Overview
Using SQL queries on the pizza sales dataset, this analysis examines various aspects of pizza sales, including overall revenue, customer preferences, and seasonality. Insights derived from this data can help the pizza store optimize its inventory, pricing, and marketing strategies.

## Findings
1. **Total Revenue**: The store’s total revenue is calculated to give a high-level view of sales performance.
2. **Average Order Value**: This KPI shows the average spending per order, which can help understand customer purchasing behavior.
3. **Top-Selling Pizzas**: Identification of pizzas generating the most revenue and quantity sold.
4. **Sales Trends**: Patterns observed in daily and monthly sales help identify peak days and months for pizza sales.
5. **Sales by Category and Size**: Breakdown of sales by pizza category and size provides insight into customer preferences.

## Suggestions
1. **Focus on High-Performing Pizzas**: Promote best-selling pizzas to maximize revenue.
2. **Inventory Adjustments**: Increase stock for popular categories and sizes, particularly during peak sales periods.
3. **Promotions on Slow Days**: Offer discounts on low-sales days to drive more orders.
4. **Optimize Menu**: Consider removing low-performing pizzas or rebranding them to boost sales.

---

## SQL Code

### KPI Queries

```sql
-- Total Revenue
SELECT 
    ROUND(SUM(total_price), 0) AS Total_Revenue
FROM pizza_sales;

-- Average Order Value
SELECT 
    SUM(total_price) / COUNT(DISTINCT order_id) AS AVG_order_value
FROM pizza_sales;

-- Total Quantity of Pizza Sold
SELECT 
    SUM(quantity) AS Total_Quantity_of_Pizzas_Sold 
FROM pizza_sales;

-- Total Orders
SELECT 
    COUNT(DISTINCT order_id) AS Total_Orders
FROM pizza_sales;

-- Average Pizza per Order
SELECT 
    CAST(CAST(SUM(quantity) AS DECIMAL(10,2)) / CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) AS DECIMAL(10,2)) AS AVG_Pizza_per_order
FROM pizza_sales;
