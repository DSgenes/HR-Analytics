# HR-Analytics

# Case Study: 

  Pinali Mandalia, an HR Manager at AtliQ Technologies, is tasked you with analyzing employee attendance data for the months 
  of April, May, and June 2022. However, manually processing and analyzing the data from multiple Excel sheets—each containing
  attendance details, leave codes, and employee names—is both time-consuming and error-prone.

  To streamline this process, you have decided to leverage Power BI to automate the attendance data transformation and analysis. 
  The goal is to build a dynamic and interactive dashboard that provides real-time insights into employee attendance, leave types, 
  and trends across different months.
  
-----------------------------------------------------------------------------------------------------------------------------------

  # Tasks : 
    Here is a brief overview of the workflow for the task:
         1. Review the data structure.
         2. Metrics to compare :
             • Working Preference of People between 'Work From Home' (WFH) and 'Working From Office' (WFO).
             • Percentage of overall 'Sick Leave %' to understand to monitor employee wellness.
               (Note : A data analyst can add more metrics to help stakeholders.)

-----------------------------------------------------------------------------------------------------------------------------------
  
# Power Query: Gathering & Transforming Data in Power BI

# Step 1 : Data Collection and Preparation 

  1. Load the workbook
  2. Import your dataset.
     
     • Download the Microsoft Excel workbook Attendance Sheet 2022-2023_Masked.xlsx.
     • At the top of the Power BI window, navigate to the Home ribbon tab.
     • In the Data group, select the Get Data option. Select Attendance Sheet 2022-2023_Masked.xlsx as the data source to import.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/5e5f657883edf45a3d38d9c054b9147c648cfda8/Screenshot%201.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/f6784b8601b981562a62e43e58bd05bbc79234fc/Screenshot%202.png)

# Step 2: Data Analysis and Exploration 

# 1. Datasets Overview:
You have four datasets, each representing attendance data for different months (April, May, and June 2022) along with an 
Attendance Key dataset. Here's a breakdown of each dataset:

   1. Apr 2022
   2. Attendance Key
   3. June 2022
   4. May 2022
      
# 1. Apr 2022:
     Contains attendance data for April 2022.
         • Employee Code: Unique identifier for each employee.
         • Name: The employee's name.
         • Date: The date of attendance for the specific employee.
         • Values: Represents attendance status or value for a particular date (could include values like Present, Absent, etc.).

# 2. Attendance Key: 
     Contains a reference for the types of attendance codes.
         • Attendance Code: Codes such as PL (Paid Leave), SL (Sick Leave), etc., which define the type of leave 
           or attendance status.

# 3. June 2022: 
     Contains attendance data for June 2022.
         • Employee Code: Unique identifier for each employee.
         • Name: The employee's name.
         • Date: The date of attendance for the specific employee.
         • Values: Similar to Apr 2022, it contains the attendance value for each date.

# 4. May 2022: 
     Contains attendance data for May 2022.
         • Employee Code: Unique identifier for each employee.
         • Name: The employee's name.
         • Date: The date of attendance for the specific employee.
         • Values: Attendance values similar to those in Apr 2022 and June 2022.
         
# 2. Automating Data Transformation in Power BI: A Step-by-Step Guide

    Goal : Now we're aiming to create a template in Power BI that can automatically apply transformations to new sheets
          (e.g., April, May, june, etc.) as they are added to your data in the future. This way, you don’t have to redo the
          transformation process every time a new sheet is added. You want to create a reusable transformation that applies
          consistently across all sheets without manual intervention.

#       • Duplicate Query
#       • Remove Unnecessary Columns
#       • Filter for Specific Month
#       • Retain Data Table
#       • Expand the Table
#       • Remove "Change Type" Step
#       • Promote First Row as Headers
#       • Remove First Unnecessary Row
#       • Rename Columns
#       • Unpivot Date Columns
#       • Remove Non-Date Values
#       • Create Parameter
#       • Create Reusable Function
#       • Invoke Function
#       • Clean Data
#       • Rename and Adjust Data Types
#       • Validate Data
#       • Clear Filters
#       • Rename Final Table

# 1. Creating a Reusable Template for Dynamic Data Transformation

     • After importing the Attendance 2022-2023 data into Power BI, go to the Power Query Editor.

# 2. Duplicating the Original Query for Reusability

     • Right-click on the query for your Attendance data in the Queries pane (on the left side). Select Duplicate. 
      This creates a copy of your original query.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/15ee029ea54de67a10866bd3db1315f3d0e77b62/Screenshot%203.png)

# 3. Deselecting Unnecessary Data for Clean Transformation

     • We don't need the Attendance Key data here because it's only for the reference purpose so I'm deselecting it.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/0251c7a89643057c043689c79db59a4f396171fd/Screenshot%204.png)

      This is to ensure that the transformation only applies to the April sheet, and any other sheets with a similar structure will 
      automatically be updated based on the same transformation.

# 4. Filtering Data for the Relevant Sheet (April)

     • Select the "Name" column, filter for "Apr 2022", and apply the transformation. It will be replicated across all sheets. 

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/0251c7a89643057c043689c79db59a4f396171fd/Screenshot%205.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/88c84600b108c73535c8f23f88df662a55bbb218/Screenshot%206.png)

# 5. Keeping Only Relevant Data by Removing Other Columns

     • To keep only the Data table and remove the other columns, right-click on the Data table column header and select 
       "Remove Other Columns". This will remove all other columns and keep only the Data table.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/88c84600b108c73535c8f23f88df662a55bbb218/Screenshot%207.png)

# 6. Expanding Data to View All Contents

     • So this is the table in which we've all the data.
     • Click on the "Table" icon to expand the sheet and reveal its contents.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/d37794ede5b365f288e26ce60af151384b989e25/Screenshot%208.png)

     • This is your April sheet Excel file.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/d37794ede5b365f288e26ce60af151384b989e25/Screenshot%209.png)

# 7. Removing Irrelevant "Change Type" Step

     • We need to remove the "Change Type" step. This is because it refers to the column names, which will vary across 
       different sheets. For example, in the "April" sheet, the columns are "April 1," "April 2," "April 3," and in the "May" 
       sheet, they are "May 1," "May 2," "May 3." Since the column names differ, we shouldn’t have any reference to them. So,
       delete this "Change Type" step to avoid issues.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/ea9d763cab7ef4e6979bf690cdb87af803bcc4fd/Screenshot%2010.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/ea9d763cab7ef4e6979bf690cdb87af803bcc4fd/Screenshot%2011.png)

# 8. Promoting First Row to Column Headers

     • You're selecting the table and choosing "Use First Row as Headers" because you want the first row of data to become the
       column headers. This ensures that the first row is treated as the header for your table columns instead of as regular data.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/9583eeee0828be9b50b76772e7f3c40c9491d429/Screenshot%2012.png)

     • When you "promote headers as first row," you're telling Power BI to treat the first row of your data as the column headers. 
       This means the values in that row will become the field names for the columns, ensuring that the table is correctly structured for 
       analysis.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/115f6375514fd529f9f05124761f446e34454aa5/Screenshot%2013.png)

     • You want to remove the first row because it doesn't serve any purpose. To do this, you can select "Remove Top Rows" and specify
       that you want to remove the first row. This will eliminate that unnecessary row from your table.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/e7164efd081181dcf1612075ca73e8f3abe9dc64/Screenshot%2015.png)

     • Upon selecting it, choose "Remove Top Rows".

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/e7164efd081181dcf1612075ca73e8f3abe9dc64/Screenshot%2014.png)

     • Specify "1" to remove the first row.This will get rid of that first row that you don't need.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/d377c10c97aaa6538554e8ab4c8e866b847d987d/Screenshot%2016.png)

# 10. Renaming Columns for Consistent Formatting

     • Rename the first column to 'Employee Code' and the second to 'Name'. The transformation we're setting up will apply automatically
       to all sheets in the file. This way, you won't need to repeat this process for May or June—it's automated."

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/df4cd9b9a8cf5896ef3c98bd512f84a378346945/Screenshot%2017.png)

# 11. Unpivoting Date Columns into a Single Column

     • Besides the 'Employee Code' and 'Name' columns, everything else is a date. I want to combine all the date columns into one single
       column, which Power BI can do. First, I’ll select the 'Employee Code' and 'Name' columns by pressing Control, then under the 'Transform'
       tab, I’ll check the available options. I’ll choose 'Unpivot Other Columns' to keep 'Employee Code' and 'Name' as they are and merge all
       the date columns into one. This is similar to the 'Transpose' concept, but in Power BI, it's called 'Unpivot.' There are three options
       under 'Unpivot Columns,' and selecting 'Unpivot Other Columns' applies this transformation.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/d30450781002dcf22b540e54aaa9a6a451aa9f8c/Screenshot%2018.png)

     • Now, all the dates are under one column, and the values are properly aligned. For example, Thanos Thakur is listed on the 1st of April.
       This is the same data as before, just in a different format. Initially, you had one name with multiple date columns. Now, you'll 
       have multiple names, but only one column for the dates. It’s essentially the same data, just presented in a different way."

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/458f57b533762910ce653495040f0c0221276a90/Screenshot%2019.png)

     • The column attribute name should be "Date," and the datatype for "Value" should be "text."

# 12. Handling Date and Text Values in the "Date" Column

     • The 'Date' column not only contain dates, but it also includes text data like 'Total Present Days,' 'Present,' 
     'Work from Home,' etc. These values aren't needed, and I could remove them manually by deselecting them via the 
      dropdown. However, if a new column is added, we'd need to repeat this process. To make it more dynamic and automated,
      thinking of changing the column’s datatype to 'Date.' This will automatically flag non-date values (like 'Holiday Off')
      as errors. Then, right-click on the 'Date' column and select 'Remove Errors,' which will automatically remove any text 
      values in the future, making the process more efficient and automated.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/83701d4ab868d98feba905b25a321f747be29bfa/Screenshot%2020.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/6dd03c7d5372d68b6dd6916d80bf80cf6af0d92e/Screenshot%2021.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/a70b04ae1e6ecf0cf38c3bd80b1e8ea74ca2df30/Screenshot%2022.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/a70b04ae1e6ecf0cf38c3bd80b1e8ea74ca2df30/Screenshot%2023.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/a70b04ae1e6ecf0cf38c3bd80b1e8ea74ca2df30/Screenshot%2024.png)

# 13. Creating a Dynamic Parameter for Date Filtering

      • After completing our transformation, we need to create a parameter. Think of a parameter as a dynamic way to filter data,
        such as selecting a specific day each month. The value of the parameter can change over time – for example, today it might
        be for April, tomorrow it could be for January, and the day after, it could be for another month. This allows you to filter
        data dynamically based on the time frame you need. To do this, I'll go to 'Manage Parameters,' select 'New Parameter,' and
        create a worksheet. Set the data type to 'Text,' and in the 'Current Value' field, I’ll add the name of the Excel worksheet,
        like 'Apr 2022.'

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/cf335e53baee10f60d44d6cf7a240ed3fea9837f/Screenshot%2025.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/94f9c2e26f931bef987c16a9a3b551dcb9a0a053/Screenshot%2026.png)

      • So, here we're applying a hard filter, like filtering for 'April 2022.' This is exactly where we’ll use a parameter. The
        parameter will allow us to dynamically filter the data based on the selected value, like 'April 2022,' and make it adaptable
        for different time frames.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/a589accac7f9be2683fe836327644be543f5239d/Screenshot%2027.png)

# 14. Using the Parameter for Dynamic Date Filtering

      • Instead of specifically filtering for 'April 2022,' we'll select the data based on the parameter worksheet.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/a589accac7f9be2683fe836327644be543f5239d/Screenshot%2028.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/a589accac7f9be2683fe836327644be543f5239d/Screenshot%2029.png)

# 15. Creating a Reusable Transformation Function

     • Now, we want to apply this transformation to all the sheets. To do that, we need to create a function. Think of it like this:
       if you add the number five to one sheet and want to add it to all sheets, you create a function for adding five. This way, 
       you can reuse the same function for all sheets. What we’ll do now is turn all the steps we've done into a reusable function.
       It’s like creating a template that you can apply to different sheets. To do this, right-click on the Template table, select
       'Create a Function', and name it 'GetData'.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/d529f20238bfa87d3d37755a23dbfc972cbb98f4/Screenshot%2030.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/d529f20238bfa87d3d37755a23dbfc972cbb98f4/Screenshot%2032.png)

# 16. Generating the Transformation Function Automatically

     • Now that we’ve created the function, what’s inside it is exactly the transformation we applied. If you had to type out all that
       code manually, it would be a lot of work, but luckily, we didn’t have to. We just clicked and dragged, and the function was 
       created for us!"

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/f187edac11574726fe5dbdb198898231876f827a/Screenshot%2033.png)

# 17. Removing Unnecessary Attendance Key Column

     • I am removing the attendance key from the original sheet.Its no longer needed.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/d4f622dcb57728bda0ce5d492537bbf243bc7789/Screenshot%2034.png)

# 18. Adding the Custom Function as a New Column

     • Add this function as a new column. To do this, go to Add Column and invoke the custom function. After creating the custom
       function, invoke it by calling the 'GetData' function name in the function query to make it available.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/643d9a8f030626da57f14dac0588926f54097e12/Screenshot%2035.png)

     • The GetData column showing Errors which it shouldn't be showing. 

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/3e140ba648cc73ae58d6785f641d451947ee84b6/Screenshot%2036.png)

# 19. Fixing Errors in the Function Output

    • The function is trying to reference a column, which it shouldn't be doing. We need to remove all steps that reference columns
      because the function will look for specific columns in the May data, but if it’s searching for something like April 1st, it 
      won’t find it in the May data. I'll go to my template data and check where the column is being referenced. For example, in 
      the 'Change Type' step, it’s referencing column names that I forgot to remove. I’ll delete that step now.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/3e140ba648cc73ae58d6785f641d451947ee84b6/Screenshot%2037.png)

    • After deleting this step , you see now all the data is available here.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/33bd2d538cf1e2548d345807ffac79eee77f1a1a/Screenshot%2038.png)

# 20. Expanding Data After Function Application

    • Let's expand the data now. Remember, these are the four columns we have: Employee Code, Name, Date, and Value. I'll go 
      ahead and expand this data accordingly.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/d24231f39ce45c793b2eeaa81d69bc828721b176/Screenshot%2039.png)

# 21. Removing Unwanted Columns

    • Delete all the other columns I don't need and keep just the 'Item' column. This column will help me identify which
      sheet the data is coming from, serving as a reference.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/4f572d82504b370362da49a387e953b4d0a7f130/Screenshot%2040.png)

    • I'll select all the unwanted columns using the Control key, then right-click and choose 'Remove Columns' to delete them

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/c73f879f129a267181728b4b5a49885bf3d6b70a/Screenshot%2041.png)

# 22. Renaming Columns and Setting Data Types

    • Renaming column names and their datatypes altegether : 'Item' to 'Sheet Name,' changing 'Employee Code' to Text, 
      'Name.1' to 'Name' as Text, 'Date' to Date, and 'Value' to Text.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/563345b7a4a16161f92d49e869f3b85c16b89fb9/Screenshot%2042.png)

    • I've selected June, so now I can see only the June data.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/708019b756b47383eb5327f245a8b10bf6d8d4be/Screenshot%2043.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/708019b756b47383eb5327f245a8b10bf6d8d4be/Screenshot%2044.png)

# 23. Selecting the Desired Data for Verification

    • I want to double-check the data, so let's randomly verify Loki Lal. For June 10th, he's listed Present. I'll check
      the Excel file, go to the June 2022 sheet, row 9, column for June 10th, and confirm he's there. This confirms the 
      data is correct. 

# 24. 12. Validating Data Consistency

    • Similarly, you can perform multiple checks to ensure everything is accurate and flowing correctly—this is 
      one level of validation.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/40ee6db57ca76ca3d3fbfa2c57089a42ad536644/Screenshot%2045.png)

    • Clear the June filter applied in the 'Sheet Name' column before loading the data to Power BI. I won't load
      all the data; I'll only load what I need. To do this, right-click on the 'Template Data' and uncheck the 
      'Enable Load' option.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/c69b44583a57bfbc17176f73bfdb2f29ccad8e49/Screenshot%2046.png)

    • Rename 'Attendance Sheet 2022-2023' to 'Final Data'. Now, I'll click 'Close & Apply' to load the data.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/3ed43b22ebaa71777da88065f891dcf7884e111b/Screenshot%2047.png)

# Conclusion : 

     What we did was take those complex Excel files with three different sheets and transform them into a usable format. 
     When you have dates across multiple columns, it's best to consolidate them into one column. This makes it easier for
     Power BI to handle transformations and formulas. If you leave dates in separate columns, you'd need to create individual
     formulas for each day and combine them, which isn't feasible. So, always remember: dates in multiple columns won't work;
     they should be in one column.

-----------------------------------------------------------------------------------------------------------------------------------------------

# Step 3 : Data Visualization

# Creating a 'Measure Table' in Power BI : 

  To create a separate 'Measure Table' in Power BI for storing your measures:
    • Go to the Home Tab.
    • Select 'Enter Data'.
    • Name the Table 'Measure Table'.
    • Leave the Data Blank: You don't need to enter any actual data here. The table will be used to store only measures.
    • Click 'Load'.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/8251e0872fa6220bd6bda8fc67c345fd0df7e2be/Screenshot%2048.png)

Now you can create your DAX measures and associate them with this new table, keeping all measures organized in one place.

# Calculating Total Working Days Excluding Non-Work Days in Power BI

To create the Total Working Days measure in Power BI, considering the removal of weekly off ("WO") and holiday off ("HO"), the formula
you've mentioned needs to be structured with DAX as follows:

# Steps to Create the Measure:

   • Define the Total Days: First, you calculate the total number of records in the dataset.
   
   • Define Non-Work Days: Then, you identify the non-working days, i.e., the days that are marked as "WO" (Weekly Off)
     and "HO" (Holiday Off) in your data.
     
   • Subtract Non-Work Days from Total Days: Finally, subtract the count of non-working days from the total days to get the 
     number of Total Working Days.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/06b4abe9e8a3c4aa900d8db5d71fb3ebb8a32e88/Screenshot%2049.png)

# How It Works:

  • Total Working Days will give you the count of all the records (days) excluding the ones that are marked as "WO" or "HO".

  • This formula helps in removing weekly off and holiday off from the total count, giving you a more accurate number of
    working days.

![image_alt]()

# Displaying Total Working Days on a Card Visual 

  • Select the Card Visual
  • Drag the Measure
  • Adjust the Formatting

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/0d492e6ea55abe52202b531cfd105b2d47aaa7c8/Screenshot%2050.png)

# Calculating Total Present Days

  To accurately calculate the Present Days measure in Power BI, we need to account for the following:
  • Days marked as "P" (Present).
  • Work from Home days ("WFH") and Half Work from Home days ("Half WFH") should also be considered as present.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/8cc50f63228cdea394fdb7c71a9f91db18f747aa/Screenshot%2051.png)

# WFH and Half WFH Count Column

  • Creating a new column in the Final Data table using the SWITCH statement is an efficient way to handle the logic
    for Work From Home (WFH) and Half Work From Home (HWFH) days, as it will simplify the aggregation and avoid complex 
    DAX calculations in the measure.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/55110c8132e3574d9f93f491a3b5ed4ff777bdfd/Screenshot%2052.png)

# Filter the 'Value' Column:

  • Click on the drop-down arrow next to the Value column in the Final Data table.
  
  • Select only the "HWFH" value. This will filter the data to show only the rows where the value is "Half Work From Home".
  
  • Check the 'WFH Count' Column

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/55110c8132e3574d9f93f491a3b5ed4ff777bdfd/Screenshot%2053.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/55110c8132e3574d9f93f491a3b5ed4ff777bdfd/Screenshot%2054.png)

  • Use the similar approach for WFH

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/55110c8132e3574d9f93f491a3b5ed4ff777bdfd/Screenshot%2055.png)

  • For rows where the value is "WFH," the WFH Count should be 1.
  
  • For rows where the value is "HWFH" (Half Work From Home), the WFH Count should be 0.5.
  
  • For other values (e.g., absent), the WFH Count should be 0.

# Creating WFH Count Measure :

  • Create another WFH Count Measure.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/15d70d8d6a0dc3ef57c7ad1b6ee3f3871581dc07/Screenshot%2056.png)

# Re-evaluating the Present Day measure

  • Since you've already created the WFH Count column and a WFH Count measure, you can simplify the Present Days formula by 
    directly referencing the WFH Count measure without needing to create a new variable for it.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/15d70d8d6a0dc3ef57c7ad1b6ee3f3871581dc07/Screenshot%2057.png)

# Create Card Visual For Present Days

  • Select Card Visual.
  • Drag and drop this measure into the Fields.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/b67d41ec4059c35b794b29c31fe7634f2af2671f/Screenshot%2058.png)

 This looks correct because your present days should be less than your working days.
 
# Creating Presence % Measure

  • To create the Presence % measure, which calculates the percentage of Present Days divided by Total Working Days, you can use 
    the DIVIDE function in DAX.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/67a63b0023578621f457346965e7e1c0eddd45f2/Screenshot%2060.png)

  • Since this is a percentage use the percentage symbol.
  
 # Create Card Visual For Presence %
 
  • Drag and drop this measure using card visual.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/b67d41ec4059c35b794b29c31fe7634f2af2671f/Screenshot%2059.png)

# Creating a Separate Month Column

  • To create a new column that shows the start of the month for each date in the Final Data table and formats it as 
  "MMM YY," you can follow these steps:

  • Create a New Column.
  • Add the formula for creating separate month column.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/6f68c382708567d67806d265b344c8c79a6c61a9/Screenshot%2061.png)

# Adding a Month Slicer

  • Now you can see the measures for different different months.
  
![image_alt](https://github.com/DSgenes/HR-Analytics/blob/20d3a07b5e789e8d1aa40a87f4e28b206279ecfd/Screenshot%2062.png)

# Final Useable Dashboard - And How These Measures Matter to them?

# Create WFH % (percentage of time people are working from home)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/a76edf49f5b9d7c69cebe124a7d0e6a631abb457/Screenshot%2063.png)

  • The WFH % measure gives you the insight of what percentage of people are working from home on a given day relative to the total present days.

    For example:

  • If 15% is the WFH % for a day, it means that out of the total number of present employees, 15% of them are working from home.
  • So, if you have 100 people in your company, 15% would translate to 15 people working from home on that day.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/ceafd899f269e9ffa6855a758890b73caaff6eef/Screenshot%2064.png)

  • This insight shows the WFH % for June, and by using the month slicer, we can compare it with other months. For example, 
    in May, the WFH % was 11%. As a co-founder of Atliq, I can see that the percentage of people working from home is higher
    in June compared to April.

  • This insight is valuable for strategic planning, especially when it comes to release schedules for clients. By analyzing the
    Presence %, we can identify periods when a significant portion of the team is absent, such as during the Diwali months of 
    October and November, when absenteeism typically increases. With this data, we can proactively communicate to clients that
    a certain percentage of our workforce will be unavailable during these months, helping us plan project timelines more effectively.

    For instance, even though we know Diwali typically causes 30%-40% absenteeism, this dashboard can provide hard data to back up our
    release planning. Additionally, it helps capture seasonal trends specific to the community. For example, if a significant portion
    of our workforce is from the Patel community and has weddings from December through mid-January, this can also be factored into
    planning. By identifying "hot zones" or peak absentee periods throughout the year, we can better align our release schedules with
    these patterns, ensuring smoother operations and better client communication.

# Create a New Column For Measuring Sick Leave %
   
   • After analyzing Presence % and WFH %, we also want to track Sick Leave % to monitor if there are any signs of increased absenteeism,
     potentially due to factors like a COVID outbreak.

   • I'm using the same approach as i did before.

![image_alt(https://github.com/DSgenes/HR-Analytics/blob/c6ac4e1fa61b7c01d90caa5d256a827b15df0f00/Screenshot%2065.png)

   • So verify this if the formula works fine for Sl and HSL.

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/a5e4f03ab9daaf607d2bc250fdd3fd23685644ea/Screenshot%2066.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/a5e4f03ab9daaf607d2bc250fdd3fd23685644ea/Screenshot%2067.png)

![image_alt](https://github.com/DSgenes/HR-Analytics/blob/a5e4f03ab9daaf607d2bc250fdd3fd23685644ea/Screenshot%2068.png)

![image_alt]()

![image_alt]()

