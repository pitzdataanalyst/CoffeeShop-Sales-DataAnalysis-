# PowerBI
### 🔢 DAX Measure for Total Revenue:

#### Total Revenue = SUMX(CoffeeShop, CoffeeShop[transaction_quantity] * CoffeeShop[unitprice])

#### NOTE: why can we not use the normal sum formula
You can use a normal SUM() formula in Power BI only if you're summing a single column, like this:
Total Sales = SUM(CoffeeShop[total_billamount])
But in your case, you don’t have a total_billamount column — you're trying to derive total revenue by multiplying two columns:

transaction_quantity

unitprice

🔍 Why SUMX() is Needed:
If you try something like:
Total Revenue = SUM(CoffeeShop[transaction_quantity] * CoffeeShop[unitprice])
It will not work because SUM() expects just one column. The expression inside the parentheses isn't a column — it's a row-level calculation.

✅ Why SUMX() Works:

Total Revenue = SUMX(CoffeeShop, CoffeeShop[transaction_quantity] * CoffeeShop[unitprice])
SUMX() is designed for such row-wise operations.
It goes row by row, calculates quantity × unit price, and then adds all those up.
