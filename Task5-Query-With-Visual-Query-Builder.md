[Home](README.md) -  [Next Task (Visualize Data) >](Task6-Visualize-Data.md)

### Task 5: Query with Visual Query

1. **Open** [Power BI](https://app.powerbi.com/)

2. In PowerBI, **click** 'Workspaces' and **select** 'FabricWarehouseWS'

3. In 'FabricWarehouseWS' workspace, **click** on 'Warehouse1' Warehouse.
4. On the Home menu, select New visual query.
5. Drag FactSalesOrder onto the canvas. Notice that a preview of the table is displayed in the Preview pane below.
6. Drag DimProduct onto the canvas. We now have two tables in our query.
7. Use the (+) button on the FactSalesOrder table on the canvas to Merge queries.

![image](https://github.com/swmannepalli/Fabric-DW/assets/84516667/d984803b-ab2b-4d59-b0c4-46e689be63d0)

8. In the Merge queries window, select DimProduct as the right table for merge. Select ProductKey in both queries, leave the default Left outer join type, and click OK.

<img width="617" alt="image" src="https://github.com/swmannepalli/Fabric-DW/assets/84516667/22fc0f34-cc57-4ab2-9d68-d5b11b5a034c">

9. In the Preview, note that the new DimProduct column has been added to the FactSalesOrder table. Expand the column by clicking the arrow to the right of the column name. Select ProductName and click OK.

<img width="479" alt="image" src="https://github.com/swmannepalli/Fabric-DW/assets/84516667/97db246c-c218-4080-8662-add00b74e6b1">

10. From here, you can analyze the results of this single query by selecting Visualize results or Open in Excel. 
   
[Continue >](Task6-Visualize-Data.md)
