# 📌 Primary Analysis (Descriptive Statistics & Data Understanding)
The primary analysis focuses on understanding the basic structure, characteristics, and distribution of the coffee vending machine sales dataset. This helps in identifying data quality, usage trends, and preparing the dataset for deeper insights.

### 1. Dataset Overview

Time Period: January 2024 to June 2024

Source: Vending machine transactions collected daily

Scope: Includes product-wise sales, transaction time, quantity sold, pricing, and total revenue generated

### 2. Data Columns & Structure

The dataset contains the following key columns:

Transaction_ID – Unique identifier for each sale

Date and Time – Timestamp of the purchase

Product_Name – Name of the beverage (e.g., Coffee, Latte, Cappuccino)

Quantity – Number of units purchased in each transaction

Price_Per_Unit – Selling price per unit

Total_Revenue – Calculated revenue (Quantity × Price)

Size – Size of drink (Small, Medium, Large)

Payment_Mode – Cash/Card/UPI (if applicable)

### 3. Missing Values & Data Quality

✅ The dataset has no missing values in key columns like Product_Name, Quantity, or Price_Per_Unit.

❌ Some records have inconsistent time formats (e.g., AM/PM missing or 24-hour format mismatch), which were cleaned during data preparation.

✅ Duplicate transaction IDs were checked and none were found.

### 4. Basic Descriptive Statistics

Total Records:  	1,49,116

Unique Products: 	9

Max Revenue (1 txn): 	₹450

Min Revenue: 	₹10

Average Revenue: 	₹4.6863671880348

Most Sold Item: 	Large Coffee


### 5. Initial Insights

Most frequent time window: 8 AM – 11 AM

Most common product: Coffee (plain)

Most preferred size: Large

Price range: ₹10 to ₹150

Majority of sales: Occur in the first half of the day, likely due to morning routines

✅ These observations give a foundational understanding of customer behavior and set the stage for further diagnostic and predictive analysis.

# 📌 Secondary Analysis (Diagnostic & Comparative)

### 1. Top-Selling Products
We analyzed the most frequently purchased product categories by evaluating the transaction count and total revenue generated.

📊 Example:

Coffee emerged as the top-selling category, contributing to 35% of total sales.

Latte Coffee followed, generating the highest average revenue per order, indicating a premium-priced item.

✅ Insight: A limited number of high-performing products account for the majority of transactions — valuable for inventory planning and promotions.

### 2. Revenue Trends Over Time
To understand sales behavior, revenue was analyzed monthly and weekly.

📊 Example:

Revenue peaked in May 2024, indicating seasonal or promotional impact.

Weekly analysis revealed consistent drops on Mondays and high spikes during weekends, suggesting customer preference for leisure purchases.

✅ Insight: This trend is useful for scheduling staff, offers, and inventory restocking.

### 3. Store Performance
If you have store_location, comparing sales across vending machines helps assess which locations perform better.

📊 Example:

The Downtown Store consistently outperformed others, contributing to 45% of total sales.

The Suburb Store had fewer transactions but higher AOV, indicating fewer but higher-value purchases.

✅ Insight: Location-specific strategies can enhance overall profitability.

### 4. Time-Based Analysis
We looked into how time influences sales across different dimensions like hour, day, and month.

📊 Example:

Peak hours: 8 AM – 11 AM (commute and morning routines).

Day with highest sales: Thrusday and Friday.

Low-traffic hours: After 6 PM, suggesting fewer late-evening customers.

✅ Insight: Ideal for running morning-exclusive combos or discounts during off-peak hours.

### 5. Customer Preferences
Analyzing preferences by size, type, or drink category gives insight into consumption behavior.

📊 Example:

Medium-sized drinks were most popular, accounting for 50%+ of all transactions.

Customers preferred hot beverages in the morning and iced drinks during noon hours.

✅ Insight: Seasonal and time-based preferences can guide dynamic pricing or bundling offers.

🎯 Expected Outcome from the Project
By the end of this analysis, we aim to:

🎯 Identify high-performing products and optimize stock levels

📈 Recognize peak sales hours/days for better service planning

💰 Calculate Average Order Value to guide pricing strategies

🧠 Understand customer behavior and preferences to influence product development

📊 Present interactive dashboards that assist managers in making data-backed decisions

💼 Strengthen my data analysis portfolio showcasing real-world, end-to-end business analysis using Excel, SQL, and Power BI


