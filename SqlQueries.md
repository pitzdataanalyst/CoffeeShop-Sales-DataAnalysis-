## DATABASE NAME: CoffeeShop

#### Created Database name as CoffeeShop import the faltfile(.csv) format into the SQl SERVER. Try to change the DATATYPE according to the requirement.

## Formulas Calculated: 

## KPI’s 

### 1.	Total Revenue
#### /* Total Revenue As  we do not have TOTALPrice column so to calculate TOTALREVENUE use below formula */

SELECT 

  SUM(unit_price * transaction_qty) AS TotalRevenue
  
FROM 

  CoffeeShop;
  
 #
 
### 2.	AverageOrderValue 
#### /* Avereage Order value , so it might happen that we have duplicates  or can say we have many transaction ids same according to the order placed by customers so to extract only the DISTINCT(Unique values ) we should use CountofDistinct values. */

SELECT 

  SUM(unit_price * transaction_qty) / COUNT(DISTINCT transaction_id) AS AVERAGE_ORDER_VALUE
  
FROM 

  CoffeeShop;

  #
 
### 3.	TotalProductSold
#### /* Total Product Sold */

SELECT 

SUM(transaction_qty) AS Total_Product_SOLD

FROM CoffeeShop;

# 

### 4.	TotalOrder

#### /* Total Orders */

SELECT 

Count(Distinct transaction_id) AS Total_Orders

FROM CoffeeShop;

#

### 5.	AverageProductPerSales

#### /* AverageProductPerSales */

Select CAST( CAST( SUM(transaction_qty)AS DECIMAL(10,2))/

CAST(COUNT(Distinct transaction_id)AS DECIMAL(10,2)) AS DECIMAL(10,2))  Avg_Product_perorder

From  CoffeeShop;

#

### 6.	Daily Trends of Orders (Day-wise)

#### /* Daily Trends of Orders */


Select 

DATENAME(DW,transaction_date) AS Order_Day,

COUNT(DISTINCT transaction_id) AS Total_Orders

FROM CoffeeShop

GROUP BY DATENAME(DW,transaction_date);

#

### 7.	Monthly Trends of Orders (Month-Wise)

#### /* Monthly Trends of Orders */


SELECT DATENAME(Month,transaction_date) AS Order_Month ,

COUNT(DISTINCT transaction_id) AS Total_Orders

FROM CoffeeShop

GROUP BY DATENAME(Month ,transaction_date)

ORDER BY Total_Orders;

#

### 8.	Percentage of Total Sales

#### /* Percentage of sales */

Select product_category, 

SUM(unit_price * transaction_qty)*100/ (SELECT SUM(unit_price * transaction_qty) FROM CoffeeShop) AS PercentageofTotalSales

FROM CoffeeShop

Group by product_category;

### 8.1.	Percentage of Total Sales With Filter of MONTH(January-December)

#### /* If we want to filter the data according to the MONTH (January=1……… December=12) than use below query in subquery*/

Select product_category,  SUM(unit_price * transaction_qty)*100/ (SELECT SUM(unit_price * transaction_qty) FROM CoffeeShop

WHERE

MONTH(transaction_date)=1 ) 

AS PercentageofTotalSales

FROM CoffeeShop

WHERE MONTH(transaction_date)=1

Group by product_category;
 
 #
 
### 9.	Percentage of Sales by Product Size 

#### /* Percentage of Sales by Product Size  */

Select Size,  SUM(unit_price * transaction_qty) AS TOtalSales , 

SUM(unit_price * transaction_qty)*100/ (SELECT SUM(unit_price * transaction_qty) FROM CoffeeShop) AS PercentageofTotalSize

FROM CoffeeShop

Group by Size

Order by  PercentageofTotalSize DESC ;

### 9.1.	 Removing Decimals upto (10,2)

#### /* for removing decimals or just for two decimals */

Select Size, CAST(SUM(unit_price * transaction_qty)AS DECIMAL(10,2)) AS TOtalSales , 

CAST(SUM(unit_price * transaction_qty) *100/ (SELECT SUM(unit_price * transaction_qty)FROM CoffeeShop) AS DECIMAL(10,2)) AS 

PercentageofTotalSize

FROM CoffeeShop

Group by Size 

Order by  PercentageofTotalSize DESC ;

### 9.2. For quarter

#### /* Filtering it for Quarter*/

Select Size,

CAST(SUM(unit_price * transaction_qty)AS DECIMAL(10,2)) AS TOtalSales , 

 CAST(SUM(unit_price * transaction_qty) *100/m(SELECT SUM(unit_price * transaction_qty)
 
FROM CoffeeShop) AS DECIMAL(10,2)) AS PercentageofTotalSize

FROM CoffeeShop

WHERE DATEPART(QUARTER,transaction_date)=1

Group by Size 

Order by  PercentageofTotalSize DESC ;
 
 #
 
### 10.	Total Revenue of products according to the Product_category

#### /* To see what is the revenue the products are giving to us*/

Select product_category ,

sum (unit_price*transaction_qty) as TotalRevenue 

from Coffeeshop

group by product_category

order by TotalRevenue DESC;


#

### 11. Top 5 & Bottom 5 according to the totalRevenue 

#### /* Top 5 Product  */

Select TOP 5 product_category ,

sum (unit_price*transaction_qty) as TotalRevenue 

from Coffeeshop

group by product_category

order by TotalRevenue DESC;


#### /* Bottom 5 products according to the total revenue */

Select TOP 5 product_category ,

sum (unit_price*transaction_qty) as TotalRevenue 

from Coffeeshop

group by product_category

order by TotalRevenue ASC;

#

### 12.	Top 5 & Bottom 5 according to the quantity

#### /* Top 5 products according to the quantity */

select TOP 5 product_category,

SUM(transaction_qty) AS Totalquantity

from CoffeeShop

group by product_category

Order by Totalquantity Desc;

#### /* Bottom 5 products according to the quantity */

select TOP 5 product_category,

SUM(transaction_qty) AS Totalquantity

from CoffeeShop

group by product_category

Order by Totalquantity Asc;

#

### 13.	Top 5 & Bottom 5 according to the transaction_id(quantity)

#### /* Top 5 products according to the transactionid(orders) */

select TOP 5 product_category,

Count(DISTINCT transaction_id) AS TotalOrders

from CoffeeShop

group by product_category

Order by TotalOrders Desc;

#### /* Bottom 5 products according to the transactionid(orders) */

select TOP 5 product_category,

Count(DISTINCT transaction_id) AS TotalOrders

from CoffeeShop

group by product_category

Order by TotalOrders Asc;

#


