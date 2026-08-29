#  Maven Market Business Performance Analysis

##  Executive Overview
The **Maven Market** project is an end-to-end business intelligence solution designed to analyze customer demographics, product categories, and regional store operations. Built using **Power BI**, this interactive dashboard transforms raw transactional data into actionable insights to drive revenue growth, optimize store inventory, and enhance profitability.

---

## 📸 Dashboard Screenshots
![Maven Market Dashboard](./Mavien%20Market.webp) 
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


    ---
# Item Sales Summary Report 
### 1️⃣ Sales & Profitability Overview
![Sales & Profitability Overview](./Item%20Sales%20Summary.png)

### 2️⃣ Volume & Item Distribution
![Volume & Item Distribution](./Sales%20summary%20report.png)

### 3️⃣ Detailed Financial Breakdown by State
![Detailed Financial Breakdown](./Sales%20By%20State.png)

##  Project Overview
The **Item Sales Summary** project is a comprehensive multi-page Power BI report designed to analyze product sales, profitability, and operational volume. It provides executive-level KPIs alongside deep granular insights across various geographic states, years, and item categories.

---

## Report Structure & Pages

1. **Sales & Profitability Overview (`Item Sales Summary.png`)**
   * High-level executive KPIs: **Total Sales ($20M)**, **Total Profit ($9.92M)**, **Cost ($9.96M)**, and **Profitability Margin (49.9%)**.
   * Multi-year trend analysis for total profit and tax-excluded figures (2013–2016).
   * Regional breakdown of performance by states and top-performing stock items.

2. **Volume & Item Distribution (`Sales summary report.png`)**
   * Operational metrics tracking **Total Quantity (1M)**, split between **Chiller Items (14K)** and **Dry Items (1M)**.
   * Total sales trajectory across years alongside top item volumes.
   * Categorized state breakdown based on performance ratings (Amazing, Average, Poor).

3. **Detailed Financial Breakdown (`Sales By State.png`)**
   * Granular table analysis detailing **Total Sales**, **Total Cost**, **Total Quantity**, and **Total Profit** across individual cities and states from 2013 to 2015.

---

##  Key Features
* **Multi-Page Navigation:** Distinct reporting pages for Executive Summary, Product Volume, and Granular Details.
* **Interactive Filtering Pane:** Slice all pages dynamically by Employee, Customer, City, Buying Group, and Sales Territory.
* **Performance Tiering:** Automated classification of states and regions into operational performance groups (e.g., Amazing, Average, Poor).

---

## Tools & Technologies Used
* **Power BI Desktop:** Dashboard construction, visual design, and page navigation setup.
* **DAX (Data Analysis Expressions):** Profitability calculations, volume counts, and dynamic measure aggregates.
* **Power Query:** Data extraction, cleaning, and attribute transformation.

---
