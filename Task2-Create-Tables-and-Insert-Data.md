[Home](README.md) -  [Next Task (Create Spark Pool) >](Task3-Create-Spark-Pool.md)

### Task 2: Create Tables and Insert Data

1. **Open** [Power BI](https://app.powerbi.com/)

2. In PowerBI, **click** 'Workspaces' and **select** 'FabricSparkWS'

3. In 'FabricSparkWS' workspace, **click** on 'MyWarehouse' Warehouse.

4. We'll create a table called DimProduct and insert data into it. To create a table using T-SQL, click on New SQL Query and paste below code,

```
CREATE TABLE dbo.DimProduct
(
    ProductKey INTEGER NOT NULL,
    ProductAltKey VARCHAR(25) NULL,
    ProductName VARCHAR(50) NOT NULL,
    Category VARCHAR(50) NULL,
    ListPrice DECIMAL(5,2) NULL
);
GO

```
5. Use the ▷ Run button to run the SQL script, which creates a new table named DimProduct in the dbo schema of the data warehouse.
6. Use the Refresh button on the toolbar to refresh the view. Then, in the Explorer pane, expand Schemas > dbo > Tables and verify that the DimProduct table has been created.
7. On the Home menu tab, use the New SQL Query button to create a new query, and enter the following INSERT statement:

```
INSERT INTO dbo.DimProduct
VALUES
(1, 'RING1', 'Bicycle bell', 'Accessories', 5.99),
(2, 'BRITE1', 'Front light', 'Accessories', 15.49),
(3, 'BRITE2', 'Rear light', 'Accessories', 15.49);
GO

```
8. Run the new query to insert three rows into the DimProduct table.
9. When the query has finished, select the Data tab at the bottom of the page in the data warehouse. In the Explorer pane, select the DimProduct table and verify that the three rows have been added to the table.
10. On the Home menu tab, use the New SQL Query button to create a new query. Then copy and paste the Transact-SQL code from below link into the new query pane.

    ```
    https://raw.githubusercontent.com/MicrosoftLearning/dp-data/main/create-dw.txt
     ``` 
11. Run the query, which creates a simple data warehouse schema and loads some data. The script should take around 30 seconds to run.
12. Use the Refresh button on the toolbar to refresh the view. Then in the Explorer pane, verify that the dbo schema in the data warehouse now contains the following four tables: <br> <br>
            DimCustomer <br>
            DimDate <br>
            DimProduct <br>
            FactSalesOrder <br>


 [Continue >](Task3-Create-Spark-Pool.md)



