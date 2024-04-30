[Home](README.md) -  [Next Task (Clone a Table) >](Task4-Clone-Tables.md)

### Task 3: Query fact and dimension tables

1. **Open** [Power BI](https://app.powerbi.com/)

2. In PowerBI, **click** 'Workspaces' and **select** 'FabricWarehouseWS'

3. In 'FabricWarehouseWS' workspace, **click** on 'Warehouse1' Warehouse.

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

   ## Create cross-warehouse queries with the SQL query editor

    For this task, we will create a new warehouse and create a DimCustomer table which will be used to create cross-warehouse queries.

   1. In Power BI workspace Click '+ New' and then select 'More options'. Select Warehouse under Data Warehouse. Provide name as 'Warehouse2' and click on Create.
   2. Click on New SQL query and copy code from [HERE](Create-DimCustomer.txt) and paste in the editor. Run the query to create DimCustomer.
   3. Go to Warehouse1, click on <img width="123" alt="image" src="https://github.com/swmannepalli/Fabric-DW/assets/84516667/fba0f735-6404-4712-8856-ac929f00484a"> and select Warehouse2 and click on Select.
   4. To execute a cross-warehouse query, from the ribbon, select New SQL query.
  
      ![image](https://github.com/swmannepalli/Fabric-DW/assets/84516667/313e4755-61f6-4ada-9029-e1db626d608d)
   5. In the query editor, copy and paste the following T-SQL code.

      ```
                   SELECT  p.ProductName,
                    SUM(CAST(Sales.Quantity AS int)) AS SoldQuantity, 
                    CONCAT(c.FirstName, ' ', c.LastName) AS Customer
            FROM [Warehouse1].[dbo].[FactSalesOrder] AS Sales
            JOIN [Warehouse1].[dbo].[DimProduct] AS p
            ON Sales.ProductKey = p.ProductKey
            JOIN [Warehouse2].[dbo].[DimCustomer] AS c
            ON Sales.CustomerKey = c.CustomerKey
            GROUP BY  p.ProductName, c.FirstName, c.LastName;
      ```
    6. Select the Run button to execute the query. After the query is completed, you will see the results.
  
       <img width="770" alt="image" src="https://github.com/swmannepalli/Fabric-DW/assets/84516667/7b8e97ab-6003-44e1-87d4-0046d6254493">

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

[Continue >](Task4-Clone-Tables.md)





