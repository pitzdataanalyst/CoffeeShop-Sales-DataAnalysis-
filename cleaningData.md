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
#







  
