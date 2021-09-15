## Part 2 - Basic Introduction to Core Features

This section focuses on getting started with Tableau and introducing you to the interface.

With Tableau opened, a new blank workbook will be created unless a previously created Tableau workbook was opened. 

## Introduction

* Tableau is an extremely powerful business intelligence application that allows its users to create in-depth visualizations in very little time.

    ![Tableau Logo](Images/01-IntroTableau_Logo.png)

  * Like Microsoft Excel, Tableau focuses extensively on allowing its users to manipulate tables of data and create visualizations without any need for additional programming.

  * Tableau also utilizes a drag-and-drop style interface so that its users can very easily create tables, charts, and perform analysis with little difficulty.

* Tableau also offers a [gallery](https://public.tableau.com/en-us/s/gallery) of projects that Tableau users have created and shared publicly.

  ![Tableau Gallery](Images/02-Installation_Gallery.png)

  * One of Tableau's features is the ability to share projects and visualizations with one's community.

  * Not only can visualizations be shared on the Tableau site, they can also be embedded on webpages.

## Connecting to Data

* Now that we have installed Tableau, open up the application and explore the many different data sources that can be connected to it.

  ![Data Sources](Images/03-LoadingData_DataSources.png)

  * Not only is Tableau able to connect to data files - like CSV, XLS, and JSON - it is also able to connect to a multitude of servers - like MySQL, MongoDB, and Google Cloud.

  * What makes this noteworthy is how Tableau allows users to mix and match data from vastly different sources without the need to translate them into something like a Pandas DataFrame. The loading, exploration, and manipulation of data is all built-in.

* Select "Excel" from the list of data sources available and load up [GlobalSuperstoreOrders2016.xlsx](Activities/01-Ins_LoadingData/Resources/GlobalSuperstoreOrders2016.xlsx) within Tableau.

  ![Tableau Tables](Images/03-LoadingData_Table.png)

  * After importing the data into Tableau, to access the individual sheets from the original Excel workbook they need to be dragged from the navigator into the main application.

* Let's do this with the `Orders` sheet and notice a preview is provided in the main area of the application.

  ![Images/load02.gif](Images/load02.gif)

* Tableau does not allow its users to change the values contained within the cells of a dataset, but it is possible to create new columns based upon the values of other columns.

  * Any and all changes made to the dataset within Tableau will not affect the original dataset. The purpose of Tableau is to create visualizations: manipulating data is not its strong-suit.

* Filtering data is very simple, however, as all you need to do is click on the "Add" button beneath the `Filters` text in the top-right corner of the application and select what column they would like to filter by.

  ![Filter Column](Images/03-LoadingData_FilterColumn.png)

  * After selecting which column to filter by, the values to filter are then chosen manually or based upon some kind of condition.

    ![Filter Values](Images/03-LoadingData_FilterValues.png)

  * Depending upon the data-type stored within a column, different filters may or may not be available. Selecting a column with a "Date" data-type, for example, allows users to filter rows based upon date ranges.

    ![Filter Dates](Images/03-LoadingData_FilterDate.png)

## Worksheets

* With a dataset linked to a Tableau workbook, we can navigate into and edit individual worksheets at the bottom of the application.

  ![Worksheets Panel](Images/05-BasicVisuals_Worksheets.png)

* Creating visualizations in Tableau is nearly identical to creating pivot tables in Excel. Users click and drag the headers of their original dataset into specific fields - Columns, Rows, Filters, etc. - in order to create a chart.

  ![Tableau Chart Screen](Images/05-BasicVisuals_ChartArea.png)

* As discussed in class `Dimensions` are categorical fields that data can be split by. `Measures` are the metrics or numbers that we would like to analyze.

* Let's drag the `Category` pill from the `Dimensions` panel into `Rows` to see how a small table containing the three categories within the dataset is created.

* By dragging `Segment` into `Rows` and placing it after the `Category` pill, the table is made slightly more complex. Now each category within the visualization has been split into three distinct parts.

  ![Images/load03.png](Images/load03.png)

* Dragging "Quantity" from the `Measurements` panel and placing it within `Columns` finally creates a true visualization: a bar chart showing the quantity of orders per segment per category.

  ![Images/load04.png](Images/load04.png)

  * Tableau has automatically aggregated `Quantity` into a sum. This will be discussed in greater detail.

* The chart can then be made more detailed by adding more elements. By adding `Market` into `Columns`, for example, multiple charts are created to show the quantity of orders per segment per category within each geographic market.

  ![Images/load05.png](Images/load05.png)

* Creating visualizations within Tableau really is as simple as that. Simply click and drag the elements that should be visualized into respective fields and Tableau will automatically create a visual based upon them.

  * If you would like to change what kind of visualization to employ, all you need to do is click the `Show Me` button at the top-right of the application and select the charting style desired.

    ![Show Me](Images/05-BasicVisuals_ShowMe.png)

* Create a new worksheet within Tableau. Drag `Sales` into the `Rows` section.

  ![Images/load06.png](Images/load06.png)

  * See that a bar chart was created that visualizes the total sales made. This is because the `Sales` pill is being measured by its sum by default.

* The type of calculation performed on a `Measures` pill can be changed by clicking on the pill, selecting "Measure" from the drop-down menu, and then picking one of the calculation types present.

  ![Change Measures](Images/05-BasicVisuals_Measures.png)

* Now drag `Order Date` into the `Columns` field to create a very basic line chart.

  ![Images/load07.png](Images/load07.png)

* Tableau has aggregated the dates at the year level. In order to expand this to include quarters, simply click on the plus symbol within the `YEAR` pill.

    ![Line Graph](Images/05-BasicVisuals_LineGraph.png)

  * Tableau, by default, visualizes at the **least** granular level. In this case, it displays the yearly results by default.

* In order to compare how Q1 has performed over the years, simply move the `QUARTER` pill before `YEAR`.

    ![Line Graph Pivot](Images/05-BasicVisuals_LineGraphPivot.png)

* The best way to learn Tableau is to dive into the application and test it out manually.


## Data Exploration Activity

* Using the `GlobalSuperstoreOrders2016.xlsx` workbook, visualize the following:

1. The customers with the highest sales amount
   ![01.png](Images/01.png)
2. A monthly timeline of sales
   ![04.png](Images/04.png)
3. Profit by region and product category (in the United States).
   ![05.png](Images/05.png)


## Data Relationships & Splitting

* In 2020 Tableau changed the default data modeling structure to the use of Relationships over Joins. 

* Relationships are a dynamic, flexible way to combine data from multiple tables for analysis similar to Joins. 

* Tableau recommends using relationships as a first approach to combining  data because it makes data preparation and analysis easier. 

* Joins are still available but should only be used when absolutely necessary.

* Some advantages of using relationships are:

  * To combine tables include making your data source easier to define, change, and reuse. 
  
  * Make it easier to analyze data across multiple tables.

  * Only querying data from tables with fields used in the current visualizaition which is more efficient.

* Relationships are an inescapable aspect of data science and are often thought to be both tedious and complex. Tableau, however, trivializes relationships to such a degree that even complex relationships can be performed in just a few clicks.

* Go back to the Data Source pane where you previously moved the "Orders" sheet into the main area. 

  * In order to merge  two datasets together, double click on the "Orders" button in the main area of Tableau, then click and drag the "People" sheet into to main area of Tableau alongside the "Orders" sheet.

  * Tableau will automatically create a relationship on the columns that contain matching values. In this case, the relationship is on the "Region" columns.

    ![Relationship Menu](Images/07-EasyRelationships_Menu.png)

  * To change how the relationship works we can open the Performance Options menu and change the Cardinality and Referenctial Integrity. Normally the default settings are ideal and we will keep these selections for this course. This same menu can be used to modify or add additional columns to merge on.

    ![Performance Options](Images/07-EasyRelationships_Performance_Options.png)

* Another interesting feature of Tableau is that columns containing text can be split so as to extract data.

  * To do this, select the column header whose values should be split, right click, and select "Custom Split" from the drop down menu.

  * Select what character to split the text on, whether to split from the beginning or end of the string, and then how many times the text should be split.

  * Here we will split the "Order ID" column on the first hyphen one time. This will extract the state in which a sale was made from the initial string.

    ![Custom Split](Images/07-EasyRelationships_CustomSplit.png)

  * New columns created this way can then be used when creating visualizations later on.

* Let's create a new worksheet and see how Tableau has added the `People` sheet with it's own set of **Dimensions** and **Metrics**. From here pills from both datasets can be used in combination.

## Relationship Activity

* Create a relation between each of the charts so that each player's data is matched up correctly.

1. Create a pair of charts that compare the potential of a club's players to their overall ability (`Overall` column). Then sort them from best to worst.

2. Create a chart that determines which nationality has the greatest acceleration on average, making sure to note how many players are from each nation in a second chart.

3. Create a chart that marks the potential of a player over time as they age.

## Additional Activity

* Create a line chart that compares the ages of patients against the total number of appointments. Then split this graph based upon gender and whether the patient showed up to their appointment. For this first step, you'll need to convert `Age` from a measure to a dimension.

* Create a pair of bar charts that compare how many patients showed up to appointments versus how many were no-shows in different neighborhoods.

* Create a stacked bar chart that compares no-shows to those who made it to appointment based upon the day of the week.

* Create a pair of line graphs that compare age versus diabetes in both men and women.


<!-- **[Part 3: Creating and Customizing Visualizations](/Intro-to-Power-BI/?lab=part-3-creating-customzing)** -->