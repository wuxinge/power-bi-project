# Adding DAX Measures 
![](new_measures_table.png)
## Steps 
1. In the DATA view, add the following calculated columns:
- In the Calendar table, add a column named "Weekend"
- In the Calendar table, add a column named "End of Month"
- Returns the last date of the current month for each row
- In the Customers table, add a column named "Current Age"
- Calculates current customer ages using the "birthdate" column and the TODAY() function
- In the Customers table, add a column named "Priority"
- Equals "High" for customers who own homes and have Golden membership cards (otherwise "Standard")   
- In the Customers table, add a column named "Short_Country"
- Returns the first three characters of the customer country, and converts to all uppercase 
- In the Customers table, add a column named "House Number"
- Extracts all characters/numbers before the first space in the "customer_address" column (hint: use SEARCH)
- In the Products table, add a column named "Price_Tier"
- Equals "High" if the retail price is >$3, "Mid" if the retail price is >$1, and "Low" otherwise
- In the Stores table, add a column named "Years_Since_Remodel"
- Calculates the number of years between the current date (TODAY()) and the last remodel date
  
2. In the REPORT view, add the following measures 
- Create new measures named "Quantity Sold" and "Quantity Returned" to calculate the sum of quantity from each data table
- Create new measures named "Total Transactions" and "Total Returns" to calculate the count of rows from each data table
- Create a new measure named "Return Rate" to calculate the ratio of quantity returned to quantity sold (format as %)
- Create a new measure named "Weekend Transactions" to calculate transactions on weekends
- Create a new measure named "% Weekend Transactions" to calculate weekend transactions as a percentage of total transactions (format as %)
- Create new measures named "All Transactions" and "All Returns" to calculate grand total transactions and returns (regardless of filter context)
- Create a new measure to calculate "Total Revenue" based on transaction quantity and product retail price, and format as $ (hint: you'll need an iterator)
- Create a new measure to calculate "Total Cost" based on transaction quantity and product cost, and format as $ (hint: you'll need an iterator)
- Create a new measure named "Total Profit" to calculate total revenue minus total cost, and format as $
- Create a new measure to calculate "Profit Margin" by dividing total profit by total revenue calculate total revenue (format as %)
- Create a new measure named "Unique Products" to calculate the number of unique product names in the Products table
- Create a new measure named "YTD Revenue" to calculate year-to-date total revenue, and format as $
- Create a new measure named "60-Day Revenue" to calculate a running revenue total over a 60-day period, and format as $
- Create new measures named  "Last Month Transactions", "Last Month Revenue", "Last Month Profit", and "Last Month Returns"
- Create a new measure named "Revenue Target" based on a 5% lift over the previous month revenue, and format as $

