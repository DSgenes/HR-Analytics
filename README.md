# HR-Analytics

# Power Query: Gathering & Transforming Data in Power BI

# Step 1 : Load the workbook

Import your dataset.

• Download the Microsoft Excel workbook Attendance Sheet 2022-2023_Masked.xlsx.

• At the top of the Power BI window, navigate to the Home ribbon tab.

• In the Data group, select the Get Data option. Select Attendance Sheet 2022-2023_Masked.xlsx as the data source to import.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/5e5f657883edf45a3d38d9c054b9147c648cfda8/Screenshot%201.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/f6784b8601b981562a62e43e58bd05bbc79234fc/Screenshot%202.png)

# Step 2: Duplicate the Query

Now we're aiming to create a template in Power BI that can automatically apply transformations to new sheets (e.g., April, May, june, etc.) 
as they are added to your data in the future. This way, you don’t have to redo the transformation process every time a new sheet is added. You want 
to create a reusable transformation that applies consistently across all sheets without manual intervention.

• After importing the Attendance 2022-2023 data into Power BI, go to the Power Query Editor.

• Right-click on the query for your Attendance data in the Queries pane (on the left side).

• Select Duplicate. This creates a copy of your original query.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/15ee029ea54de67a10866bd3db1315f3d0e77b62/Screenshot%203.png)

• I don't need the Attendance Key data here because it's only for the reference purpose so I'm deselecting it.

![image_alt]()

This is to ensure that the transformation only applies to the April sheet, and any other sheets with a similar structure will automatically be updated based on the same transformation.

• Select the "Name" column, filter for "Apr 2022", and apply the transformation. It will be replicated across all sheets. 

![image_alt]()

![image_alt]()

• To keep only the Data table and remove the other columns, right-click on the Data table column header and select "Remove Other Columns". This will remove all other columns and keep only the Data table.

![image_alt]()

• So this is the table in which we've all the data.

![image_alt]()

• Click on the "Table" icon to expand the sheet and reveal its contents.

![image_alt]()

• This is you April sheet Excel file.

![image_alt]()





