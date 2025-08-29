1. LOAD DATA & CLEAN DATA in PowerQuery 
   Dates Columns to Date Format, not Text
   Remove Duplicates
   Build the initial Data Model
   Rename FACT Table and DIMensional Tables

AFTER CLEANING THE DATA
Insert a New Table for Date Dimension

2. CREATE VIRTUAL TABLES
After cleaning the data, first we created virtual tables for different goals:
- a Date Dimensional Table to have a Date Hierarchy
- a Data Table to have a Slicer to select between different KPIs: Sales, Gross Profits, Quantity
- a Measure Table to hold all the Measures created specifically for this goal:
YTD cumulative measures
PYTD cumulative measures
YTD-PYTD
Switches that show PYTD whenever needed


3. Create CUSTOM MEASURES with DAX functions and code logic:
Quantity = SUM(Fact_Sales(quantity))
Sales = SUM(Fact_Sales(sales_USD))
COGs = SUM(Fact_Sales(COGS_USD))
Gross Profit = [Sales]-[COGS]


PYTD_Sales = CALCULATE([Sales],SAMEPERIODLASTYEAR(Dim_Date[Date]),Dim_Date[Inpast]=TRUE)
PYTD_Quantity same formula
PYTD_Gross_Profit same formula
PYTD_Quantity = CALCULATE([Quantity],SAMEPERIODLASTYEAR(Dim_Date[Date]),Dim_Date[Inpast]=TRUE)
YTD_Sales = TOTALYTD([Sales],FACT_Sales[Date_Time])
YTD_Gross Profit = TOTALYTD([Gross Profit],FACT_Sales[Date_Time])
YTD_Quantity





4. Create SWITCHES as New Measures with DAX logic
SWITCH to PYTD values
Switch 2 to YTD values




