
# 📊 Dashboard Project – Manufacturing Plant Sales & Gross Profit Analysis

**Project Overview**  
This dashboard presents [short description: e.g. “an interactive performance overview of sales across regions over time”, “customer support tickets by issue type and resolution times”, etc.]. The goal is to [what the dashboard helps with: decision-making, spotting trends, identifying bottlenecks, etc.].
**Project Title:** Manufacturing Plant Sales & Gross Profit analyis
**Theme:** Sales Performance Dashboard
**Objective:** To create an interactive dashboard that provides insights into sales data, with YTD and PYTD explicit measures and time comparaison, switches and conditional formating.

---

## 🚀 Main Steps & Skills Demonstrated

Here are the key steps in building this dashboard, along with the skills you’ll see in action:

| Step | Description | Skills Used |
|---|---|---|
| **1. Data Collection & Import** | Acquire data from [source(s) — e.g. CSVs, database, API] | Data import, working with file formats, basic ETL (Extract-Transform-Load) |
| **2. Data Cleaning & Transformation** | Clean missing values, filter irrelevant data, standardize formats (dates, categories, etc.) | Pandas / Power Query / SQL, handling missing data, normalization, data types |
| **3. Data Modeling / Aggregation** | Aggregate data into useful metrics (totals, averages, rates), possibly calculating derived fields | GroupBy operations, calculated fields, handling hierarchies/time series |
| **4. Visualization Design** | Build charts/tables/maps to show trends, comparisons, highlight key metrics | Data viz library or tool (e.g. Matplotlib / Seaborn / Power BI / Tableau), choosing chart types, designing layout |
| **5. Interactivity & Filters** | Add interactivity: filters by category/date, tooltips, drill-downs | Dashboard tool skills (filtering/slicing/dicing), user experience design |
| **6. Validation & Testing** | Verify correctness of numbers, test edge cases, double check labels, test performance on large data | Data validation, Python or notebook checks, sanity-checking results |
| **7. Presentation & Export** | Polish design, add titles/legends, export or share the dashboard | UI polish, storytelling, sharing/exporting (PDF, web, embedded) |

---

## 🛠 Skills Highlighted

- Data cleaning / wrangling  
- Working with time-series data  
- Calculated / derived metrics  
- Interactive visualizations  
- Dashboard layout & design principles  
- Testing / validating data  
- Presentation & communication of insights

---

## 📸 Screenshots

Below are some screenshots from the dashboard. (Replace the image paths with your own.)

![Dashboard Overview](https://github.com/user-attachments/assets/f7923cbc-d4ac-48b8-96d6-ad1df8fa6cb6)
*Figure: main overview screen showing Quantity over time.*

![Plant Dashboard - view 2](https://github.com/user-attachments/assets/79e0c56d-04b4-4894-8db4-3bd1949e2a40)
*Figure: switching for Sales Measures and other Year.*

---


## 🛠️ Step-by-Step Dashboard Creation

### 1. **Data Import and Data Transformation in PowerQUery**

**Description:**
Importing data from various sources and preparing it for analysis.

**Skills Demonstrated:**

* Connecting to data sources (e.g., Excel, SQL Server)
* Data transformation using Power Query
* Handling missing values and data types
* Dates Columns format to Date, not Text.
* Remove Duplicates on the Primary Key
* Build the initial Data Model
* Rename the FACT Table and Dimensional Tables

**Screenshot:**
![Data Import](https://example.com/data_import_screenshot.png)

---

### 2. **Creating Explicit Measures with DAX and Virtual Tables in PowerQuery**

**Description:**
Developing custom measures to calculate key metrics.

**Skills Demonstrated:**

* Creating calculated columns and measures
* Understanding row context and filter context
After cleaning the data, first we created virtual tables for different goals:  
* a Date Dimensional Table to have a Date Hierarchy
* a Data Table to have a Slicer to select between different KPIs: Sales, Gross Profits, Quantity
* a Measure Table to hold all the Measures created specifically for the Explicit Measures  
  
After, we create Explicit Measures in DAX that will be the back-bone of the interactivity of this dashboard :
* Creating Totals with DAX formulas
Quantity = SUM(Fact_Sales(quantity))  
Sales = SUM(Fact_Sales(sales_USD))  
COGs = SUM(Fact_Sales(COGS_USD))  
Gross Profit = [Sales]-[COGS]  
* YTD cumulative measures
* PYTD cumulative measures
* YTD-PYTD
PYTD_Sales = CALCULATE([Sales],SAMEPERIODLASTYEAR(Dim_Date[Date]),Dim_Date[Inpast]=TRUE)  
PYTD_Quantity same formula  
PYTD_Gross_Profit same formula  
PYTD_Quantity = CALCULATE([Quantity],SAMEPERIODLASTYEAR(Dim_Date[Date]),Dim_Date[Inpast]=TRUE)  
YTD_Sales = TOTALYTD([Sales],FACT_Sales[Date_Time])  
YTD_Gross Profit = TOTALYTD([Gross Profit],FACT_Sales[Date_Time])  
YTD_Quantity  
  

**Screenshot:**
![DAX Measures](https://example.com/dax_measures_screenshot.png)

---

### 3. **Building Relationships**

**Description:**
Establishing relationships between tables to enable seamless data analysis.

**Skills Demonstrated:**

* Defining one-to-many and many-to-many relationships
* Managing relationship cardinality
* Utilizing star schema design

**Screenshot:**
![Relationships](https://example.com/relationships_screenshot.png)

---

### 4. **Designing Visualizations**

**Description:**
Creating various visual elements to represent data effectively.

**Skills Demonstrated:**

* Using different visualization types (e.g., bar charts, line graphs, KPIs)
* Formatting visuals for clarity
* Implementing slicers and filters

**Screenshot:**
![Visualizations](https://example.com/visualizations_screenshot.png)

---

### 5. **Enhancing Interactivity**

**Description:**
Adding interactive elements to allow users to explore data dynamically.

**Skills Demonstrated:**

* Implementing drill-through and tooltips
* Setting up bookmarks and buttons
* Configuring dynamic titles and measures
* Create SWITCHES as New Measures with DAX logic
- Switch 1 to PYTD values
- Switch 2 to YTD values


**Screenshot:**
![Interactivity](https://example.com/interactivity_screenshot.png)

---

### 6. **Finalizing and Publishing**

**Description:**
Polishing the dashboard and preparing it for sharing.

**Skills Demonstrated:**

* Reviewing and testing the dashboard
* Publishing to Power BI Service
* Sharing and collaborating with stakeholders

**Screenshot:**
![Final Dashboard](https://example.com/final_dashboard_screenshot.png)



---

## 🧠 Key Takeaways

* Mastery of data import and transformation techniques.
* Proficiency in creating complex DAX measures.
* Understanding of data modeling and relationships.
* Ability to design intuitive and interactive dashboards.

---

## 🧪 How to Run the Project (if applicable)

1. Clone this repo:  
   ```bash
   git clone https://github.com/your-username/your-dashboard-repo.git
```

2. Install PowerBI Desktop
3. Launch dashboard in PowerBI service or open dashboard in tool PowerBI



---


---





