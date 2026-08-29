#  Maven Market Business Performance Analysis

##  Executive Overview
The **Maven Market** project is an end-to-end business intelligence solution designed to analyze customer demographics, product categories, and regional store operations. Built using **Power BI**, this interactive dashboard transforms raw transactional data into actionable insights to drive revenue growth, optimize store inventory, and enhance profitability.

---

## 📸 Dashboard Screenshots

---

##  Report Structure & Key Insights

### Customer Demographics
Focuses on identifying high-value customer segments and evaluating purchasing behavior.
* **Key Metrics:** Total Customers, Active Customer Rate, Average Revenue per Customer.
* **Visuals:** Income & occupation distributions, customer geographic mapping (USA, Mexico, Canada), and marital/gender breakdowns.
* **Technical Highlights:** Dynamic slicers and custom hierarchies (`Country > State > City`) for intuitive drill-down exploration.

###  Store & Product Operations
Evaluates product profitability and physical store efficiency to streamline operational decisions.
* **Key Metrics:** Total Transactions, Quantity Sold, Return Rates, Margin per Product.
* **Visuals:** Matrix of Revenue/Cost/Profit by Category, Store Performance Treemap, Top 10 Dynamic Product Rankings.
* **Technical Highlights:** Data integration with `Returns_Data` to compute actual return rates alongside sales performance.

### Financial Performance & Target Tracking
Tracks core financial metrics against targets and historical benchmarks.
* **Key Metrics:** Total Revenue, Total Cost, Net Profit, MoM (Month-over-Month) Growth Rate.
* **Visuals:** Executive KPI Cards with trend indicators, Revenue Trend Line with forecasting, Regional Filters.
* **Technical Highlights:** Time-Intelligence DAX functions (`DATEADD`, `SAMEPERIODLASTYEAR`) for historical evaluation.

---

##  Data Architecture & Modeling

The project utilizes a **Star Schema** to ensure fast query execution and optimal dynamic filtering across all visuals.

* **Fact Tables:** `Sales_Data`, `Returns_Data`
* **Dimension Tables:** `Customers`, `Products`, `Stores`, `Calendar`
* **Relationships:** $1:*$ (One-to-Many) single-direction filtering for data integrity.

---

## Tech Stack & Advanced Techniques

* **Power BI Desktop:** Core tool for visualization and dashboard delivery.
* **Power Query (M):** Data cleaning, unpivoting, column merging, and data type transformations.
* **DAX (Data Analysis Expressions):** Advanced calculated columns and measures using iterators (`SUMX`) and time intelligence.

### Sample DAX Measures

```dax
// Total Revenue Calculation
Total Revenue = 
SUMX(
    Sales_Data, 
    Sales_Data[quantity] * RELATED(Products[product_retail_price])
)

// Month-over-Month Revenue Growth
MoM Revenue Growth = 
VAR CurrentRevenue = [Total Revenue]
VAR PreviousMonthRevenue = 
    CALCULATE(
        [Total Revenue], 
        DATEADD('Calendar'[Date], -1, MONTH)
    )
RETURN
    DIVIDE(CurrentRevenue - PreviousMonthRevenue, PreviousMonthRevenue, 0)
