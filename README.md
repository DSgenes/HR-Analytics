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

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/0251c7a89643057c043689c79db59a4f396171fd/Screenshot%204.png)

This is to ensure that the transformation only applies to the April sheet, and any other sheets with a similar structure will automatically be updated based on the same transformation.

• Select the "Name" column, filter for "Apr 2022", and apply the transformation. It will be replicated across all sheets. 

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/0251c7a89643057c043689c79db59a4f396171fd/Screenshot%205.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/88c84600b108c73535c8f23f88df662a55bbb218/Screenshot%206.png)

• To keep only the Data table and remove the other columns, right-click on the Data table column header and select "Remove Other Columns". This will remove all other columns and keep only the Data table.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/88c84600b108c73535c8f23f88df662a55bbb218/Screenshot%207.png)

• So this is the table in which we've all the data.

• Click on the "Table" icon to expand the sheet and reveal its contents.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/d37794ede5b365f288e26ce60af151384b989e25/Screenshot%208.png)

• This is your April sheet Excel file.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/d37794ede5b365f288e26ce60af151384b989e25/Screenshot%209.png)

• We need to remove the "Change Type" step. This is because it refers to the column names, which will vary across different sheets. For example, in the "April" sheet, the columns are "April 1," "April 2," "April 3," and in the "May" sheet, they are "May 1," "May 2," "May 3." Since the column names differ, we shouldn’t have any reference to them. So, delete this "Change Type" step to avoid issues.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/ea9d763cab7ef4e6979bf690cdb87af803bcc4fd/Screenshot%2010.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/ea9d763cab7ef4e6979bf690cdb87af803bcc4fd/Screenshot%2011.png)

• You're selecting the table and choosing "Use First Row as Headers" because you want the first row of data to become the column headers. This ensures that the first row is treated as the header for your table columns instead of as regular data.

![image_alt]()

• 

![image_alt]()

