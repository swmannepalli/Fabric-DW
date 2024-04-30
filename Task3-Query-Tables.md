[Home](README.md) -  [Next Task (Query Tables) >](Task3-Query-Tables.md)

### Task 3: Query fact and dimension tables

1. **Open** [Power BI](https://app.powerbi.com/)

2. In PowerBI, **click** 'Workspaces' and **select** 'FabricSparkWS'

3. In 'FabricSparkWS' workspace, **click** on 'MyWarehouse' Warehouse.

4. Most queries in a relational data warehouse involve aggregating and grouping data (using aggregate functions and GROUP BY clauses) across related tables (using JOIN clauses).
    Create a new SQL Query, and run the following code:

   ```
   SELECT  d.[Year] AS CalendarYear,
         d.[Month] AS MonthOfYear,
         d.MonthName AS MonthName,
        SUM(so.SalesTotal) AS SalesRevenue
        FROM FactSalesOrder AS so
        JOIN DimDate AS d ON so.SalesOrderDateKey = d.DateKey
        GROUP BY d.[Year], d.[Month], d.MonthName
        ORDER BY CalendarYear, MonthOfYear;
   ```
   ## Create a view

Views in Microsoft Fabric data warehousing are a powerful tool for encapsulating complex queries, managing data access permissions, simplifying data access, and facilitating cross-database querying.

Create a new SQL Query, and run the following code:

 ```
  CREATE VIEW vSalesByRegion
AS
SELECT  d.[Year] AS CalendarYear,
        d.[Month] AS MonthOfYear,
        d.MonthName AS MonthName,
        c.CountryRegion AS SalesRegion,
       SUM(so.SalesTotal) AS SalesRevenue
FROM FactSalesOrder AS so
JOIN DimDate AS d ON so.SalesOrderDateKey = d.DateKey
JOIN DimCustomer AS c ON so.CustomerKey = c.CustomerKey
GROUP BY d.[Year], d.[Month], d.MonthName, c.CountryRegion;

 ```

[Continue >](Task3-Query-Tables.md)





