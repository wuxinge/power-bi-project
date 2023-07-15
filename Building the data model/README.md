# Building the Data Model 

## Steps 
1. In the MODEL view, arrange your tables with the lookup tables above the data table
  * Connect Transaction_Data to Customers, Products, and Stores using valid primary/foreign keys
  * Connect Transaction_Data to Calendar using both date fields, with an inactive "stock_date" relationship
  * Connect Return_Data to Products, Calendar, and Stores using valid primary/foreign keys
  * Connect Stores to Regions as a "snowflake" schema
2. Ensure:
  * All relationships follow one-to-many cardinality, with primary keys (1) on the lookup side and foreign keys (*) on the data side
  * Filters are all one-way (no two-way filters)
  * Filter context flows "downstream" from lookup tables to data tables
  * Data tables are connected via shared lookup tables (not directly to each other)

Notes:
  * Fact tables contain numerical values or metrics used for summarization (sales, orders, transactions, pageviews, etc.)
  * Dimension tables contain descriptive attributes used for filtering or grouping (products, customers, dates, stores, etc.)
  * Fact tables should connect through shared dimension tables, not directly to each other
      * Be aware of two-way filters
      * Example: 
        Product: water bottle 
        Return in Territories one and two 
        Sold in territories one, two, three, and four 
        
        Filter the product from the product lookup table and allow that context to pass through both the sales data and returns data   tables. It means that our territory lookup would be receiving two different sets of filter context. 
        
        The returns data table would be telling the territory lookup to filter down to territories one and two. 
        
        The sales data table would be telling the territory lookup to filter down to territories one, two, three and four. 
        
        We can’t pass conflicting filter context to the same table. (Ambiguity)
        
3. Hide all foreign keys in both data tables from Report View, as well as "region_id" from the Stores table (to force users to filter using primary keys in dimension tables)
   * prevent users from filtering using invalid fields, reduce clutter, or to hide irrelevant metrics from view
4. Formatting
   * Update all date fields (across all tables) to the "M/d/yyyy" format using the formatting tools in the Modeling tab
   * Update "product_retail_price", "product_cost", and "discount_price" to Currency ($ English) format
   * In the Customers table, categorize "customer_city" as City, "customer_postal_code" as Postal Code, and "customer_country" as Country/Region
   * In the Stores table, categorize "store_city" as City, "store_state" as State or Province, "store_country" as Country/Region, and "full_address" as Address
  
[](ERD.png)
