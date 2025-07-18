# ✅ What Formulas to use and how to use them.

## 1- Total Amount(Bill) to be calculated as we have feilds like:

#### transaction_qty &  unit_price

    Formula to be used: 

    Total_Amt= transaction_qty*unit_price

## 2- How to Extract Month,Day,Week,Hours from the given Data
  How did I achieved this :
  
  #### Select the column to be used transaction_date  
  
  Go to ----> Add Column for Date Tab and select (Month,Day ,Week)
  
  #### Select the column to be used transaction_time
  
  Go to ----> Add Column for Date Tab and select (Hours)
  
  ## 3- How to Pivot 
   How did I achieved this :
   
    Add Pivot Table into the Excel sheet using the existing data model 
    
    It will givw you two options and we will select a table as a database option in orange colour.
    
#### To check on hourly basis what is the sales we are getting?

      Use rows--> Hours
      Use Values--> Transaction id (so we never use sum for any ID , as eg if there is ADHAARCARD for two people so we have to count as tewo ,we dont do Sum of it)
      
      In case of Price ---> It should be always SUM 
      
      I have changed the Currency of Total_Bill_Amt into dollars (GOTO---> Home-->Number-->NumberFormat)
      
  #### Using only Sumof transaction_Quantity(transaction_qty)
  
    Because in transaction_id we are only getting the count of people ordering the products, but we are not able to know the exact amount of products has been ordered by people.
    
  ## 4- Creating Charts 
  
   How did I achieved this :
   
   Select the Pivot Table 
   
   Select Chart Option of 2dLine with marker as , *if there is an Hourly Base OR Time base Graphs we have to show* , than always choose **2D line chart**

## 5- Calculate on the basis of Weekely 
 
    How did I achieved this :

    Create a new Table using Total_Bill_Amt and Day Name 
    
    As we have to calculate the Total Amount on the basis of Weekely transactions done or Orders Done 

  #### Creating new column for Month,Day of week 
    
    Getdata--->Launch Power Query Editor 
    
    It will give two columns
    
    1-Month It will give the NUMBER for MonthNAME(january,Feburary)
    
    2-Day of week (0-6) (Monday-Sunday)
    
   #### Fixing the Dayname , MonthName in Ascending and Desending Orders 
    
      **Launch Power Pivot --> Select Month Name column --- > Sortcolumn --> Month**
      
        Launch Power Pivot --> Select Day Name column --- > Sortcolumn --> Dayofweek**
        
        Launch Power Pivot --> Select Toatl_Bill_Amt column --- > Number --> select Dollar**
        
## 6 -  Product category and Sum of total bill 
  
  Create a new Pivot Table for the same because if we need to calculate what kind of Product Category is giving what sales.
  
  And for the same pivot table create a chart related to it using 2D column and bar chart 
  
  Creating new Pivot Table to know the sales of which product is giving what kind of revenue,so using Product_type and Total_bill_Amt we can calulate 
  
  So to know the **TOP 5 Products** select the product type --> top10--> Change it to TOP 5 

## 7 -  Location wise Sales Data 
  
Create a new Pivot Table for Location and Total_Bill_amt to know that how much sales we are getting from all the Locations 

Similarly Create a new Pivot Table for Location and Transaction_id (count)

Calculating the footfall using transaction_id 

#### Creating Charts 

Which Product category is taking the biggest percentage so use **PieChart**

What is the Footfall_store of Coffee Shop so use **BarChart**

What is the Top 5 products of Coffee  Shop so use **BarChart**

Format the Charts Accordingly 

## 8- What kind of Size people are choosing for coffee (Lg,Rg,Sm)

  Create a Pivot Table for Size and Transaction_id (count)
  
  Use **Pie Chart** for the Analysis 

## 9- Adding And Creating Measures(Mandotary KPI's) 

#### How to crete New Measures in excel:

**Power Pivot --> Measures**

1- What was the Total sales 

**SUM([Total_Bill_Amt])**

2- What was the FootFall (The value should not be duplicate so that is why we have to use **DISTINCTCOUNT**

**DISTINCTCOUNT([Transaction_id])**

3- What is the Average Bill PerPerson 

**=SUM(Table1[Total_Bill_Amt])/DISTINCTCOUNT(Table1[transaction_id])**

4- What is the Average Order PerPerson

**=SUM(Table1[transaction_qty])/DISTINCTCOUNT(Table1[transaction_id])**
#
