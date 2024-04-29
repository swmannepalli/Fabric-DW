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


 [Continue >](Task3-Create-Spark-Pool.md)



