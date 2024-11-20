# Introduction
📈 Having any amount of data doesn't mean necessarily that we can understand and comprehend what is telling us. A person, group, an industry, is always in the need of new tools and procedures to ensure an efficient way to extract and catch all the useful information they maight have. 🔦So if your up for it check out this two examples that show a ⚙📶basic transformation of raw data to a more interesting data set: [Sample Superstore File](/Sample%20Superstore.pbix) And also an easy way to 📈📊visualize the most important insights and indicators: [Retail Analysis Sample](/Retail%20Analysis%20Sample.pbix). 

# Background
👩‍💻Using the data to facilitate the decision making is one of the main objectives of a business regardless the size, type of industry, niche market, etc. Being able to obtain performance metrics, analytics such as process mining, reporting and data visualization, improves significantly the way in wich you can comprehend how an organization operates, design and execute any strategy.🧩  


🧠One of the most recently upgraded and popular tool used in business intelligence (and in this project) around the world is Microsoft Power BI. "*Power BI is designed to be used by business professionals with varying levels of data knowledge.*" 

In this repository you may find the following .pbix files: "Sample Superstore" and "Retail Analysis Sample". 📂The first one was populated with data stored in a Excel file wich you can check out from Learnit OneDrive [Excel File](https://learnitanywhere-my.sharepoint.com/personal/learnitfiles_learnitanywhere_onmicrosoft_com/_layouts/15/onedrive.aspx?id=%2Fpersonal%2Flearnitfiles%5Flearnitanywhere%5Fonmicrosoft%5Fcom%2FDocuments%2FAnytime%2FMedia%20Team%2FExternal%20Team%2FAssignments%2FExercise%20Files%2FPower%20BI%20Exercise%20Files%2Ezip&parent=%2Fpersonal%2Flearnitfiles%5Flearnitanywhere%5Fonmicrosoft%5Fcom%2FDocuments%2FAnytime%2FMedia%20Team%2FExternal%20Team%2FAssignments%2FExercise%20Files&ga=1). The second file is mainly to show different ways of data visualization that you can apply, in the Visualization Process section of this README file I'm going to do my best to illustrate how to make them with a breif description of the data fields used.

For the main part of this project I wanted to answer the following questions:
1.  Is the data ready to be used to extract precise and helpful information?
2.  What kind of insights can be extracted to help the business decision making?
3.  What are the basic visualizations to present the insights and information we extracted?

# Tools I Used
- **Microsoft Power BI Desktop**: Even though it is a tool desinged for data visualization and business intelligence, it also has the capability to organize, transform and calculate data. 

- **Git & GitHub**: Essential for sharing SQL scripts and analysis, ensuring collaboration and project tracking.

# Utilization and Readability
The "Sample Superstore.pbix" file contains the result of every editing, cleaning, transforming and calculating step I'm about to describe. Initially there were only three tables under the names of: "Orders", "Returns" and "Users" and each contained more or less columns with different fact or dimension data. As you follow through this project I'll try my best to give you visual support for a better understanding of what is going on and how we get the final product. First I will give most of the description and explanations followed by the corresponding images, so let's start!

## Clean and Transform

### Data Shape Transformation
First of all it is necessary to take care of any inaccurate title or name given to any table or column. We need to avoid uncertainty when manipulating data references to avoid confusion or misleading information at the final product. As you can see in each table there are several columns representing a specific data type or information category, for example in the "Orders" table we can see columns like: *Order Priority*, *Unit Price*, *Customer Name* or *Product Name*. In this case both table and column name is clear, understandable and related to the information they contain so 
there is no need of any change at the moment. 

The ones that need change are: "Users" table name as it has information about managers, "Column1" and "Column2" titles need to be replaced by the first row of the table; sometimes Power Bi doesn't detect the first row of an Excel file as titles so we have to promote that first row to a column header.

- Renaming the "Users" table is as simple as locate the table in the "Fields" pane and right click on it, choose "Rename" from the shortcut menu and replace it with "Managers" for this particual case. I also changed the column "State or Province" to only "State" in the "Orders" table as it only has those names.  

![](image.png)

![](image-1.png)

- To promote the first row as column headings go to "Transform Data", located in the "Home" tab. In the "Home" tab of the "Power Query" window locate at the right side the option "Use First Row as Headers" and click on it. 

|**Optional**|
|-------------|
|In the "Managers" table I duplicated the column "Manager" to include the last name and have a more precise way to identify each person. Changed the column headers to "Manager First" and "Manager Last" by right clicking on each column and selecting the rename option. I also replaced the duplicated values in the new column one at a time as it is a short list; just right click on every cell and choose the "Replace Values..." option.|
|

Now it is important to select the columns you need, the specific information you want within the tables in order to be more efficient in the way you manipulate the data. 

- Select the "Orders" table. In the "File" tab locate at the center the "Choose Columns" option and select it. Uncheck the boxes you don't want to manipulate. In this case I didn't want *Row ID*, *Order Priority*, *Product Base Margin* and *Quantity ordered new*. 


Last part of shaping this data is filtering and sorting. As you may already know, we are looking towards a more specific and easy to handle data set. 

- Click on the auto filtering arrow next to the column header "State". I wanted only the information from: *Arizona*, *California*, *Florida*, *New Jersey* and *New York*. At the top of the check box menu select also the "Sort Ascending" option to visualize the data in the alphabetical order of the states.


### Enhance Structure of Data
Merging data from different tables is one of the best and basic methods to improve the data model. It allows you to increase your comprehension of how complex your business is.

At the far right in the "File" tab in Power Query there is "Merge Query", click on the arrow next to it and select "Merge Query as New".

We want a data set that relates the managers of the "Managers" Table with the region they are responsable for (
"Orders" Table). 

![alt text](image-2.png)

- Merge the "Orders" and "Managers" table referencing the only column they have in common: "Region". Select a **Right Outer Join** as we want all from the "Managers" table matching the data of "Orders" Table. It will appear on the left side the new query as "Merge1". Change the name to "Orders by Region". Select this new query and scroll all the way to the right, click on the expand button next to the column header to visualize the data. 

- Rename the last two columns deleting only the "Manager." part of the header. Next, click on the arrow next to the "Manager.Region" column header and uncheck the Central option to sort out the null values; also choose the "Sort Ascending" option. 

**Use the same method to create a new query to relate "Orders" and "Returns" tables and name it: "Returned Orders".**

![alt text](image-3.png)

### Profile and Examine Data
Power Query Editor has profiling tools that you can use in order to support the quality of the data you are manipulating. It is important that every extract of information you use or present has an in-depth assesment of how you got to it. 

On the "View" tab there are the following profiling tools:

1. Column quality: It tells whether the column is "valid", if there is errors or empty cells using a percentage.

2. Column distribution: It shows graphically how many unique and distinct values are in each column. It also has an option to remove duplicate values if necessary. 

3. Column profile: It opens a panel at the bottom underneath the data set and show some descriptive statistics of the column you select. 

![alt text](image-4.png)

**Check and Apply changes in the Power Query Editor Window.**

## Desing Data Model
As we move on transforming our data it becomes more important the designing and development of the data model for proper performance and scalability. We will continue to make the data more accurate and intentional as possible in order to tackle many of the common issues such as: *relationships, security and performance*.

### Transforming and Creating Tables
1. You can start by giving a "standard" format to the data in the "Orders" table. I picked the columns: **"Discount", "Unit Price", Shipping Cost", "Order Date" and "Ship Date"** to apply a data format, but it can be done to several others. 
    
    - Click on any cell of the column you want to apply a format. In the "Column tools" tab at the top, in the formating group, select the arrow next to "Format" and choose the best option for the data in the column you are working on.

![](image-5.png) 
- For the columns: **"Region", "State", "City" and "Postal Code"** apply a specific data category for each. Locate in the "Column tools" tab the properties group and choose the corresponding category for each of the previuos mentioned columns.

![](image-6.png)

2. Break down the "Orders" table into two different kinds: Facts and Dimensions (Numeric and Descriptive). This is a procedure under the premise *"One large table is not the answer for an effective data model."*

    - **Customer Dimensions query**: Go to the Power Query Editor and make a copy of the "Orders" table. Choose only the columns related to customer information as this is a descriptive table. It is important that you assign a *primary key* field; a unique identifier that makes each record unique (in this case I chosed the "Customer ID" column). Rename the query, I did "DimCustomer"; Dim is for "Dimension".

![](image-7.png)
 
    
I followed the same procedure to make the query: **DimProduct** adding a index column with the header "Product ID" ("Add column" tab) starting from 1.

![](image-8.png)

3. Location hierarchy in the "Orders" table to group related fields together and increase data manipulation performance.

    - Start with the broadest category in terms of column ("Region") and end with the narrowest ("Postal Code"). Drop down the "Orders" table in the Fields pane, locate "Region" and right click on it. Select "Create hierarchy". Locate the "State" field, right click on it and choose "Add to hierarchy" and select the only option available. Do the same with "City" and "Postal Code".

![](image-9.png)
    

### Create Model Relantionships/Review of Interface
Before making any change in the relationships of your data set be sure to check in "Options and Settings" that you have available the "Relationships" options. 

![](image-10.png)

I have the following relationships configuration, with most of the tables linked to each other by the field or fields they have in common or the primary keys assigned. Take your time to check them using the "Manage relationships" option in the "Home" tab at the top. 

![](image-11.png)

### Enforce Row-Level Security (RLS)
*"RLS in Power BI can be used to restrict data access for given users. Filters restrict data  access at row level, and you can define filters within roles."* 

I did set up a role that allows a user assigned to this specific role previuosly to view data of the "Orders" table just for the "East" region. 

- In the "Modeling" tab, at the security group, choose the manage roles. Click "Create" and name it "East", make sure you select the "Orders" table. Now select the column "Region", use the "=" symbol to create the filter and write or select "East". Apply and Save.

- Test the role by choosing the "View as" in the same security group, check the "East" role and click "Ok". Check the "Data view" and you will see the table filtered out by the region showing only the data of the East region.

![](image-12.png)

![](image-13.png)

**Always be sure to save the changes you make.**

## Create Model Calculations Using DAX
Is a collection of functions, operators and constants that can be used in a formula, or expression, to calculate and return one or more values. It allows to perform dynamic analysis at cell, row and any related data.

### Creating Calculated Tables and Columns 
We can use a calculated table to store extracted information that isn't provided in the raw/edited data unless it is calculated. A table with data about the total of different orders is extremely important for a bussines. It helps with *inventory levels*, *order management*, *order processing*, *economic order quantity* among others. So in this instance I created a new table to display the distinct orders made. You can create a new table selecting the option in the "Modeling" tab.

In the formula bar write the following: 

![](image-14.png)

In a more detailed manner, creating calculated columns might increase the value of the information used as you go further in the underlying meaning of the data your business is capturing. 

I created two new columns inside the "Orders" table: one calculating the day difference in order and shipments and the next one creating a rank from highest (starting on 1) to lowest of the sales made; you can calculate the other way around just changing the order field inside the function used. Please check the images underneath to see the DAX functions and syntax I used for each.

![](image-15.png)

### Creating Measures and Quick Measures
Measures are often called *virtual calculations* and they don't become part of the data set. They calculate when you add them to a report visualization. This tool is great when the file size is an issue and replace a calculated column or table. The distinction between measures and quick measures is that the first one you have to build it from scratch and last one is like a template inside Power Bi.

Starting with a quick measure, I wanted from the "Orders" table an average sales table based on customer segment. 

- Right click on the "Orders" table in the fields pane and select "New quick measure". Choose the calculation you need (in this case I selected "Total for category (filters not applied)" as we already process the "Orders" table filtering and editing and we don't want this to affect the calculation). Locate the sales field inside the orders table and choose it, change the "sum" for "average in the predetermined calculation field. Select also the Customer segment field for category and click "Ok".

The quick measure is now inside the "Orders" table and you can call it when you are creating your report visualization.

![](image-16.png)

Creating a measure from scratch is similar to the procedure as the DAX functions. Now I wanted an average sales per product category in the Orders table. Right click on the table and select "New measure".

As I said previuosly it is similar to creating a DAX function, so please check out the following images to see the syntax, functions and variables used.

![](image-17.png)

### Time Intelligence Functions and Key Performance Indicators (KPI)
This file doesn't have any date table and without this we can't use a time intelligence function. The first step will be the creation of a date table. 

- Create a new table and in the formula bar use the function "CALENDARAUTO" (this function creates a column scanning the able selected to register the earliest and last date data entry).

- Now we want to add new columns to the table. They are going to store the year, quarter and month of the first column separately. Check the next images with all the syntax to do it. 

![](image-18.png)

![](image-19.png)

Finally mark down the table right clicking on it and select "Mark as date table". Then choose the first column and press Ok. Relate this table to the "Orders" table on "Model" view based on the "Order Date" field. 

**Notes**: 

1. After creating the relationship if you go to "Data" view you may see that the "Date" column is filled with errors. To fix it select the column and in the formula bar delete both instances of ".[Date]"

2. I created a column to show the end of the month for each order and another to show the end of the quarter for each order. It is the same procedure using in the formula bar "ENDOFMONTH" and "ENDOFQUARTER" functions. Format both of them and that is it.

![](image-20.png)

**Save the changes and close the file**.

**Open "Retail analysis sample" file** as it's needed for the last topic of this section. 
Go to "Data" view and expand the Sales table. There are several comparative columns in this data, two in particular are of interest for the *key performance indicator*: "Total Units Last Year" and "Total Units This Year".

This gives us the ability to compare the progress of a business. If you click on the "Time" table you'll see it has a fiscal month column that is a help to visualize the comparison between years.

Before you create a KPI, it is better to start building the report without the framework of a KPI. That is because once you convert the report into a KPI you won't be able to have sorting capabilities.

This is how it was created the visualization in the KPI page on the report you are seeing: 
1. Let's start locating the "Total Units This Year" column in the "Sales" table and drag it to the canvas. In the "Time" table locate the "Fical Month" column and drag it over the bar visual created previuosly. 

2. At this point it is not a KPI but rather a clustered column chart. This is when you would want to do any sorting or filtering before in gets converted into a KPI. I sorted it in Ascending by fiscal month.


3. In the visualization pane locate the KPI option (make sure you have selected the bar chart) and press it to convert the chart into a KPI. Underneath the visualization pane locate the "Target goals" field. We want to drag the "Total Units This Year" column in there. Now the KPI is completed.

![](image-21.png)

## Optimize Model Performance
This are some of the basic concepts and data modeling best practices necessary to improve a data model for enterprice-level performance.

### Direct Query
Most of the time when using Power BI Service/Desktop, as we do in other similar apps, we are used to importe all the data from another data source. Sometimes it becomes a problem as it creates a large file size and causes some performance issues. Refreshing data, depending on the case, can be a lengthy process perfomed many times a day.

If it is necessary for business decision making to have reports that reflect the latest data, then we better use *DirectQuery*. Is a tool that allow us to connect directly to data in the original source repository (SQL Server, Azure Analysis Services, etc.) and no data is imported into Power BI.


### Variables 
When data modeling, writing and debugging DAX calculations can be time consuming. Compound expressions can involve the use of nested functions and possibly the reuse of expression logic.

Using variables to store the result of an expression can be passed as an argument to other expressions and will improve the readability of the DAX function or query, simplify debugging and reduce complexity.

Please make sure to see the images underneath were a measure was created to calculate the total sales from the "Orders" table using variables in the formula bar.

![](image-22.png)

# Visualization Process
The "Retail Sample Analysis" file is populated with 5 tables with different data categories (Facts and Dimensions): Sales, District, Item, Store and Time. Most of the Facts tables already have calculated fields in order to create reports and charts either from scratch or with designs shared in Power BI Service. 

When doing a report or chart there is a basic method that will help assure the precision and truthfulness of the data displayed:

- Use of precise and specific data fields
- Design and Create
- Enhance the report
- Configure visual fields and Format properties

Before making anything in a report it is important to make sure if you are clear on what are the things you want to show. Please take a moment to read the extensive amount of documentation on the internet about what visual tools are made for a specific kind of purpose or data/information. We want to pass down the insights in a simple, direct, effective and precise manner.

Most of the configuration, formating and filtering is done within the following panes in Power BI Desktop: Visualizations and Filters.

![](image-23.png)

Now I will give some notes on particular charts so you can explore more freely the file and get a better (interactive) experience manipulating the fundamentals of Power BI visualizations.

1. Pie chart: Add other tooltips (underneath the visualization pane), pertinent information you'd like to see when you hover over a slice of the pie. 

2. Clustered Column: Use the filters pane to dissect the data into different data categories and show a more intricate report.

3. Some of the charts have a Drill Through option underneath the visualizations pane. Use it when you want to focuse on a specific dimension data and point to other report pages that are focused to get details that are filtered to that context.

4. Add conditional formating to any chart to indicate and highlight context on performance. Right click on one of the fields you used for your chart and select Conditional formating; create your condition(s) and apply.

5. Add local or global slicer to filter the chart(s) you are working on. Click on the empty space on the canvas, locate in the visualizations pane the "Slicer" and select it. Add the filter(s) you want. If the slicer is going to be used in other charts not only in one, then go to the View tab and at the far right select Sync slicers; finally choose the charts you want the slicer to be available.

![](image-24.png)

![](image-25.png)

**Verify always if there is a special formating you need to apply considering the people you are presenting to such as a Color blind palette.**

# What I Learned
As I went through this project it became more and more evident to me the next statements:

- It doesn't matter if you can capture many data categories or a large quantity of information, when you are looking to obtain specific and valuable insights the most important thing is: reliable data sources and a clean data set.

- Complex and intricate don't always mean efficient or better. Most of the time keeping it short, simple and precise is the best practice. It applies to transforming and cleaning data, and also when it comes to visualize the information.

# Conclusion
1. It was clear from the beginning that the data set needed several steps of transformation, modeling, sorting and filtering before even imagining a basic indicator with reliable information.

2. We extracted the following indicators that help managers with business decisions: Calculated table with the distinct orders made, days between order and shipment and ranking of sales. Measure and quick measure with the average sales per product category and based on customer segment. Tables for dimension data and Facts data. A *key performance indicator* with the "Total Units This Year" vs "Total Units Last Year".

3. KPI, Histogram, clustered Bar chart, Bar Charts with slicer just to name a few of all the kind of visualizations Power BI includes and many more you can explore or aggregate within the Power BI Service.

