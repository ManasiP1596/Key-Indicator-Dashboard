# Key-Indicator-Dashboard
- Comparative Study of Countries: Key Indicators Dashboard
2 Datasets:
Primary Dataset: Insurance Sample Dataset, Secondary Dataset: Global Financial Development Dataset (Used Data Blending) for exporting both in Tableau File.
Edit Blend Relationship. Go to Data – Edit blend relationship- custom: Country- Country, Code- iso3, Year- Year.
Steps to Perform: 
Work Sheet: Countries by Income
From Primary Data Source (Insurance Sample Dataset): Drag & drop Country into Detail For the 1 unknown value: click on Edit locations and in matching location – enter South Korea Select Fill Map from Marks card Drag & drop Country Code into Label 
. From Secondary Data Set: Drag & drop income into Colour Drag & drop income into Filters Show income Filter Edit Filter in Legend to Show Multiple Values (drop down) (Go to Analysis- Legend- show income (colour)) Rename filter to “Select Income Group” ( on right hand side where income filter is displayed click on dropdown arrow and edit title).
Work Sheet: KPI Table 
1.	In Primary Data Source (Insurance Sample Dataset): Change the datatype of “Year” field to date from number.
2.	Create Parameter, select from dropdown, name ‘Create Parameter’- select list- add values from-: 1: Life Insurance Share, 2: Market Share, 3: Penetration, 4: Ratio of Reinsurance Accepted 5: Retention Ratio.  Keep Data Type: String, click ok.
3.	Create parameter “select year’, values: 01-01-2006: 2006, 01-01-2007: 2007, 01-01-2008: 2008, 01-01-2009: 2009, 01-01-2010: 2010, 01-01-2011: 2011, 01-01-2012: 2012, 01-01-2013: 2013, 01-01-2014: 2014, 01-01-2015: 2015, 01-01-2016: 2016. Data Type: Date, click ok.
4.	Now create Calculated field for 5 parameters created, 
a)	Selected Category: CASE [Select Category] WHEN 1 THEN [Life insurance share] WHEN 2 THEN [Market share > Total] WHEN 3 THEN [Penetration > Total] WHEN 4 THEN [Ratio of reinsurance accepted > Total] ELSE [Retention ratio > Total] END
b)	 Selected Year: IF YEAR([Year]) = YEAR ([Select Year]) THEN [Selected Category] END
c)	Previous Year: IF YEAR([Year]) = YEAR ([Select Year]) - 1 THEN [Selected Category] END
d)	Growth Percentage: AVG ([Selected Year]) – AVG ([Previous Year])
e)	Growth Indicator: IF [Growth %] > 0.000 THEN "Positive" ELSEIF [Growth %] < -0.000 THEN "Negative" ELSE "No change" END
5.	Show Parameters: Select Category and Select Year
6.	Select Growth Indicator, Previous Year, Selected Year and drag it into text column and display text table.
7.	Edit alias names of “Selected Year” and “Previous Year” to: Selected Period Value and Comparison Period Value respectively.
8.	 From the rows shelf, on Measure Names, Sort in manual order: Selected Period Value, Comparison Period Value, Growth % 10. Format the KPI table to increase the font size: Right click on the table and select format Choose Font  Select font size as 15 apply borders for rows and columns. 
9.	 Double click on the title and from Insert  select Parameters. Select Category. Format the title, as required.
Work Sheet: Growth Indicator
Now create 2 calculated flied:
1.	1. Show Parameters: Select Category & Select Year 
2.	2. In marks shelf: Select Shapes 
3.	3. Under directory: C:\Users\Manasi\Documents\My Tableau Repository\Shapes, create a new folder with name “Growth Shapes” and keep the growth indicator icons/shapes for Positive, Negative and No Change. Name the images of shapes/icons accordingly (Positive, Negative and No Change).  (download image from google).
4.	 Drag & Drop “Growth Indicator” calculated field into shapes.
5.	 5. Select Shapes and change the default folder to “Growth Shapes” where the growth indicator icons have been saved. 
6.	6. Select Shape - Assign Palette -Apply 
7.	7. Check if based on growth %, the growth indicators are changing and adjust as required. For No change, use 2006 year.

Work Sheet: Trend Line 
1. Use Primary Data Source (Insurance Sample Dataset): 
2. Create a line chart by selecting Year (continuous data type) into columns and “Selected Category” into rows. Change the aggregation into average for “Selected Category” from the default sum. 
3. Show Parameters: Select Category & Select Year 
4. Drag & Drop Year into Pages shelf to create motion chart. Edit Title of the motion chart to Year in the cards shelf (right side). 
5. In marks shelf, select circle(o) instead of automatic (line chart). 
6. Select Show History click downward arrow 
Select All Under Show: select Trail do formatting on the required line thickness and colour. 
8.	In marks shelf, select Shapes and choose suitable arrow to indicate the progression of the trend line and select suitable colour for the shape (other than the trend line colour).
DASHBOARD:
Select size of board to automatic. Range- Automatic.
Dashboard: Key Indicators Dashboard 
1. Select size of dashboard to automatic 
2. Drag & drop Country by Income sheet into the dashboard 
3. Using dashboard object, create a webpage – with Wikipedia website provided in the assessment: https://en.wikipedia.org/wiki/Country 
4. Create a Dashboard Action - Go to URL to select the country in the map and to view the Wikipedia website using the following link: https://en.wikipedia.org/wiki/Country and run action as “Select”. 
5. Drag & drop other sheets (KPI Table, Growth Indicator & Trend Line) into the dashboard and make them floating. Then, adjust their positions and sizes as per the required layout.
 6. Delete filter of Income (coloured from the Countries by Income worksheet) from the dashboard. 
7. Click on Select Income group filter and using more options, apply this filter to Apply to Worksheets - Selected Worksheets - All on Dashboard. 
8. Select “Countries by Income” sheet in the dashboard and choose More options. Select Use as Filter. 
9. Now go to Dashboard Actions and Select the Filter 1 (generated) and choose to edit. Source sheet as “Countries by Income” with Run action on “Menu” and choose target sheets as all sheets with clearing the selection will “Show all values”. 
10. Right click on each worksheet available in dashboard and go to Lay out on the top left side to select the border. 
11. Also, edit title of each worksheet available in dashboard and change their background colour to the required colour: rgb (0,255,255). 
12. Click on Show Dashboard title at the left bottom of the dashboard and edit the title as “Key Indicators Dashboard”. Format it as required. Also, change the background colour in the layout section as rgb (0,255,255). 
13. In the dashboard, select Presentation Mode or F7 and select the following: a) Income Group: All b) Year: 2016 c) Category: Life Insurance Share d) For the Year Motion chart, selection year 2016.
