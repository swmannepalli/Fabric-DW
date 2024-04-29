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


[Continue >](Task3-Query-Tables.md)





