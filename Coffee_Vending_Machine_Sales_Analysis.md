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
