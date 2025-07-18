# How I cleaned the Data Given 
     Load the data in EXCEL TRANSFORM DATA (LOAD DATA)
### Columns given:

* transaction_id
* transaction_date
* transaction_time(timestamp also given)
* transaction_qty
* store_id
* store_location
* product_id
* unit_price
* product_category
* product_type
* product_detail
  
### Columns Created:
* Size
* Total_Bill_Amt
* Month Name
* Day Name
* Hour
* Week of Month
  
### Measures in excel:
* Sales
* Total Footfall
* Average_Bill_PerPerson
* Average Order_PerPerson

## 1- What Data Should be cleaned according to the Analysis
 We have to remove the dates given in the transaction_time(timestamp also given)
 
    How did I achieved this :
    
    Goto ----> Extract ---> Text After Demeliter 
    
## 2- We have to create new column as per Lg,Rg,Sm from product_detail
  How did I achieved this :
  
  Added Conditional Column (Name-Size)
  
      If the product_detail contains Lg (output - Large)
  
       ElseIf the product_detail contains Rg (output - Regular)
   
        ElseIf the product_detail contains Sm (output - Small)
    
            Else Not Declared (If not defined as Not Declared it will show NULL value , as in future maybe we need to use product_deatils so there should be no NULL's around
        
## 3- We have to remove the Lg,Rg,Sm from product_detail
  How did I achieved this :
  
  Go to ----> Replace Values and give the input as Lg,Rg,Sm Respectively and replace these characters with nothing just a blank space.
  
  But now after replacing the values it leaves the blanks in the column of product_details , so trim the space using **Trim** Function

## 4- Total Amount(Bill) to be calculated as we have feilds like:

#### transaction_qty &  unit_price

#### Formula to be used: 

#### Total_Amt= transaction_qty*unit_price

## 5- How to Extract Month,Day,Week,Hours from the given Data
  How did I achieved this :
  
  #### Select the column to be used transaction_date  
  
  Go to ----> Add Column for Date Tab and select (Month,Day ,Week)
  
  #### Select the column to be used transaction_time
  
  Go to ----> Add Column for Date Tab and select (Hours)
  
  ## 6- How to Pivot 
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
    
  ## 7- Creating Charts 
  
   How did I achieved this :
   
   Select the Pivot Table 
   
   Select Chart Option of 2dLine with marker as , *if there is an Hourly Base OR Time base Graphs we have to show* , than always choose **2D line chart**

 ## 8- Calculate on the basis of Weekely 
 
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
        
  ## 9 -  Product category and Sum of total bill 
  
  Create a new Pivot Table for the same because if we need to calculate what kind of Product Category is giving what sales.
  
  And for the same pivot table create a chart related to it using 2D column and bar chart 
  
  Creating new Pivot Table to know the sales of which product is giving what kind of revenue,so using Product_type and Total_bill_Amt we can calulate 
  
  So to know the **TOP 5 Products** select the product type --> top10--> Change it to TOP 5 

  ## 10 -  Location wise Sales Data 
  
Create a new Pivot Table for Location and Total_Bill_amt to know that how much sales we are getting from all the Locations 

Similarly Create a new Pivot Table for Location and Transaction_id (count)

Calculating the footfall using transaction_id 

#### Creating Charts 

Which Product category is taking the biggest percentage so use **PieChart**

What is the Footfall_store of Coffee Shop so use **BarChart**

What is the Top 5 products of Coffee  Shop so use **BarChart**

Format the Charts Accordingly 

## 11- What kind of Size people are choosing for coffee (Lg,Rg,Sm)

  Create a Pivot Table for Size and Transaction_id (count)
  
  Use **Pie Chart** for the Analysis 

## 12- Adding And Creating Measures(Mandotary KPI's) 

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







  
