# 🛒 E-Commerce Sales Analysis – Power BI Project

### 📊 Project Overview  
This Power BI project provides an end-to-end analysis of **E-Commerce Sales Data** — from data transformation and modeling to DAX calculations and visualization.  
The main objective is to gain insights into sales performance, profit trends, customer patterns, and regional performance using interactive dashboards.

---

## 📁 Dataset Information  
The project uses three CSV files as data sources:

- **List of Orders.csv**  
- **Order Details.csv**  
- **Sales Target.csv**

---

## 🔧 Data Transformation (Power Query Editor)

Performed data cleaning and transformation steps to prepare the data for modeling and analysis:

- Restricted *List of Orders* to the **first 500 rows** for efficiency.  
- Converted:
  - *Order Date* → **Date**
  - *Amount* & *Target* → **Fixed Decimal Number**
- Formatted *CustomerName* to **Proper Case**.  
- Merged *City* and *State* → new **Location** column (`City, State`).  
- Created **Profit Margin (%)** = `Profit / Amount`.  
- Added **Profit Status** column:
  - `Profit < 0` → Loss  
  - `Profit = 0` → Break-Even  
  - `Profit > 0` → Profit  
- Merged *List of Orders* and *Order Details* on **Order ID** → new table *Orders Data*.  
- Identified and handled **missing values** and **duplicates**.  
- Sorted *Order Date* in **descending order** to analyze recent trends.  
- Filtered dataset (e.g., focused on **Tamil Nadu** for regional analysis).  
- Grouped and aggregated:
  - Count of orders per Order ID  
  - Average profit by Category  
  - Total amount by Sub-Category  
  - Monthly target total from Sales Target table  

---

## 🧩 Data Modeling  

Established relationships between tables:

- **List of Orders ↔ Order Details** using *Order ID*  
- **Order Details ↔ Sales Target** using *Category*  

All relationships were activated and validated using the *Manage Relationships* view in Power BI.

---

## 🧮 DAX Calculations  

### 🧱 Calculated Columns
- **Category Type** = `Category & " - " & Sub-Category`  
- **Revenue per Order** = `Amount * Quantity`  
- **Sales Category** = `IF(Amount > AVERAGE(Amount), "Above Average", "Below Average")`  

### 📏 Calculated Measures
- **Order Count** = `COUNTROWS('Order Details')`  
- **Average Profit (Delhi)** =  
  `CALCULATE(AVERAGE('Order Details'[Profit]), 'List of Orders'[City] = "Delhi")`  
- **Year-to-Date (YTD) Sales** =  
  `TOTALYTD(SUM('Order Details'[Amount]), 'List of Orders'[Order Date])`

---

## 📈 Data Visualizations  

Created an interactive Power BI dashboard featuring the following visuals:

| Visualization | Description |
|----------------|-------------|
| **Clustered Column Chart** | Compare actual sales vs. sales targets by Category |
| **Donut Chart** | Show Maximum Profit Margin by Sub-Category |
| **Line Chart** | Monthly Sales Trend over time |
| **Scatter Chart** | Compare Profit vs. Quantity by Sub-Category |
| **Cards & Multi-Row Cards** | Display Total Sales, Total Target, and Minimum Target per Segment |
| **Matrix Table** | Compare Sales vs. Targets by Category and Month |
| **Map Visualization** | Display Total Sales by City (Geographic Analysis) |
| **Treemap** | Show Sales Distribution by Sub-Category |
| **Funnel Chart** | Visualize Order Count by State |

---

## 💡 Key Insights  

- Identified **top-performing cities and categories** driving the majority of profit.  
- Highlighted **loss-making sub-categories** for business improvement.  
- Compared **actual sales vs. targets** to measure goal achievement.  
- Showed **regional performance** and **monthly growth trends**.  
- Visualized **overall profit margin** across the product mix.

---

## 🧠 Tools & Technologies Used  

- **Power BI Desktop**  
- **Power Query Editor** (for ETL & data cleaning)  
- **DAX (Data Analysis Expressions)**  
- **CSV Files** as data source  

---

## 👨‍💻 Author  

**Your Name**  
📧 vallianand001@gmail.com
🌐 https://www.linkedin.com/in/valli-a-89466b20b/ 

---



