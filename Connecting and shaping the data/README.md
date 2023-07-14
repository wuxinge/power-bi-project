# Connecting and Shaping the Date 

## Steps 
1. Connected to 7 tables with 6 cvs files and 2 cvs files in a folder.
   - Objective: use different types of connectors/connectivity modes to get data into Power BI

| Files        |     Format      | Tables in Power BI |
| ------------- |:-------------:| :-----:|
| MavenMarket_Customers| cvs| Customers |
| MavenMarket_Products | cvs    |   Products |
| MavenMarket_Stores   | cvs     |  Stores |
| MavenMarket_Regions  | cvs | Regions |
| MavenMarket_Calendar | cvs   |   Calendar|
| MavenMarket_Returns  | cvs   |  Return_Data  |
| MavenMarket Transactions | folder | Transaction_Data|

*** MavenMarket Transactions folder contain the MavenMarket_Transactions_1997 and MavenMarket_Transactions_1998 cvs files. 

2. Named each table and ensured that headers have been promoted.
3. Confirmed that data types are accurate.
   * all id columns should be whole numbers
   * "quantity" should be whole numbers
   * "customer_acct_num", "customer_postal_code" and "product_sku" should be text
   * "product_retail_price" and "product_cost" should be decimal numbers
  
4. Transformed tables by using different query editing tools
   * Add new columns
     * Add a new column named "full_name" to merge the the "first_name" and "last_name" columns, separated by a space
     * Create a new column named "birth_year" to extract the year from the "birthdate" column, and format as text 
     * Create a conditional column named "has_children" which equals "N" if "total_children" = 0, otherwise "Y"
     * Add a calculated column named "discount_price", equal to 90% of the original retail price
     * Add a calculated column named "area_code", by extracting the characters before the dash ("-") in the "store_phone" field
     * Add a calculated column named "full_address", by merging "store_city", "store_state", and "store_country", separated by a comma and space (hint: use a custom separator)
       
   * Transform columns
     * Replace "null" values with zeros in both the "recyclable" and "low-fat" columns 
     * Select "product_brand" and use the Group By option to calculate the average retail price by brand, and name the new column "Avg Retail Price"
     * Round "discount_price" to 2 digits
     * Use the statistics tools to return the number of distinct product brands, followed by distinct product names
