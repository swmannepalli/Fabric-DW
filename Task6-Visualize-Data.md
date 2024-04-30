[Home](README.md) 

### Task 6: Visualize Data

1. **Open** [Power BI](https://app.powerbi.com/)

2. In PowerBI, **click** 'Workspaces' and **select** 'FabricSparkWS'

3. In 'FabricSparkWS' workspace, **click** on 'Warehouse1' Warehouse.
4. We need to define a data model before creating report. 
5. At the bottom of the page in the data warehouse, select the Model tab.
6. In the model pane, rearrange the tables in your data warehouse so that the FactSalesOrder table is in the middle, like this:

<img width="781" alt="image" src="https://github.com/swmannepalli/Fabric-DW/assets/84516667/c9b7410c-fdc9-4171-b3ed-ec33d81d55c6">

7. Drag the ProductKey field from the FactSalesOrder table and drop it on the ProductKey field in the DimProduct table. Then confirm the following relationship details:
         Table 1: FactSalesOrder
         Column: ProductKey
         Table 2: DimProduct
         Column: ProductKey
         Cardinality: Many to one (*:1)
         Cross filter direction: Single
         Make this relationship active: Selected
         Assume referential integrity: Unselected
8. Repeat the process to create many-to-one relationships between the following tables:

         FactSalesOrder.SalesOrderDateKey → DimDate.DateKey
   
9. When all of the relationships have been defined, the model should look like this:

<img width="731" alt="image" src="https://github.com/swmannepalli/Fabric-DW/assets/84516667/f8f2b48a-81b7-4a35-8b10-d506f8b44d03">

## Create Report

1. Now you’re ready to build a report and make this dataset available to others. On the Home menu, select New report. This will open a new window, where you can create a Power BI report.
2. Under Data section, expand FactSalesOrder and select Quantity. Expand DimProduct and select ProductName.
   
<img width="494" alt="image" src="https://github.com/swmannepalli/Fabric-DW/assets/84516667/0cfe65b3-dd3a-49cf-90f3-30d5ac797e74">

3. Select visual type as Clustered Column Chart. Click on File and Save the report. Provide name of the report as ProductQuantity and Save it.

<img width="316" alt="image" src="https://github.com/swmannepalli/Fabric-DW/assets/84516667/b759fedf-01a5-41e7-879d-593fbb392c60">

4. Now when you go back to the workspace, you should see the saved report along with two Warehouses.

   <img width="1739" alt="image" src="https://github.com/swmannepalli/Fabric-DW/assets/84516667/9047b379-6d25-4742-865b-64c66f83384f">


[Home](README.md) 

