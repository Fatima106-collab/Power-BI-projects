# AdventureWorks Sales & Business Performance Analysis

## Executive Overview
The **AdventureWorks** project is a comprehensive, multi-page Business Intelligence solution built with **Power BI** to analyze sales revenue, profitability, product performance, return rates, and customer behavior (2020–2022)[cite: 3, 4, 5]. Designed with interactive parameters, custom report-page tooltips, and a normalized data model, it empowers decision-makers to track KPIs against targets and drill down into granular product and customer segments[cite: 2, 3, 4, 5, 6].

---

## 📸 Dashboard Screenshots

### 1️⃣ Executive Overview (`Over View`)
![AdventureWorks Overview](./AdventureWorks_Overview.png)

### 2️⃣ Product Details & Target Tracking (`Product Details`)
![AdventureWorks Product Details](./AdventureWorks_Product_Details.png)

### 3️⃣ Customer Demographics & Segmentation (`Customer Detail`)
![AdventureWorks Customer Detail](./AdventureWorks_Customer_Detail.png)

### 4️⃣ Data Model & Schema Architecture
![AdventureWorks Data Model](./AdventureWorks_Data_Model.png)

### 5️⃣ Custom Report Tooltips
| Category Tooltip | General KPI Tooltip |
| :---: | :---: |
| ![Category Tooltip](./AdventureWorks_Category_Tooltip.png) | ![General Tooltip](./AdventureWorks_Tooltip.png) |

---

## Report Structure & Key Insights

### 1. Executive Overview (`Over View`)
Provides a high-level snapshot of overall business health and product category performance:
- **Executive KPIs:** **Total Revenue ($25M)**, **Total Profit ($10M)**, **Profit Margin (41.97%)**, and **Return Rate (2.17%)**[cite: 3].
- **Monthly Performance Cards:** Tracks **Monthly Revenue ($1,826,987 | +3.34% vs. Goal)**, **Monthly Orders (2,146)**, and **Monthly Returned (167)** with built-in area trendlines[cite: 3].
- **Category & Product Analysis:** Breaks down orders by category (led by *Accessories* and *Bikes*) and highlights top products alongside conditional formatting for return rates, plus dynamic cards for **Most Ordered Subcategory (*Tires and Tubes*)** and **Most Returned Subcategory (*Shorts*)**[cite: 3].

### 2. Product Details (`Product Details`)
Dedicated to product-level evaluation and what-if scenario modeling:
- **Target Gauges:** Visualizes **Revenue vs. Target**, **Profit vs. Target**, and **Orders vs. Target** for selected items (e.g., *Sport-100 Helmet, Blue*)[cite: 4].
- **Interactive Parameters:** Features a **Price Parameter** slider and a **Metric Parameter** selector (*Orders, Profit, Revenue, Return, Return Rate*) to dynamically switch chart metrics[cite: 4].
- **Profitability & Order Trends:** Compares **Profit vs. Adjusted Profit Trend** alongside historical order volume[cite: 4].

### 3. Customer Detail (`Customer Detail`)
Focuses on customer value, demographics, and top-spender identification:
- **Customer KPIs:** Tracks **17.42K Active Customers** and **$1.43K Average Customer Value**[cite: 5].
- **Demographic Breakdown:** Donut charts analyzing **Total Orders by Income Level** (*Low, Mid, High*) and **Total Orders by Occupation** (*Professional, Skilled Manual, Management, Clerical, Manual*)[cite: 5].
- **Top 100 Customers Ranking:** Interactive table displaying Customer Key, Full Name, Total Orders, and Total Revenue with dynamic highlight cards for the selected customer[cite: 5].

### 4. Custom Report-Page Tooltips (`Category ToolTip` & `Tool Tip`)
- Hovering over categories or data points reveals a dark-themed summary card displaying exact **Revenue ($24,914,587)**, **Profit ($10,457,715)**, **Cost ($14,456,871)**, **Orders (25,164)**, **Return Rate (2.17%)**, and a trend chart[cite: 6, 7].

---

## Data Architecture & Modeling
The report is powered by a **Snowflake / Star Schema** connecting fact tables to lookup dimensions via single-direction One-to-Many ($1:*$) relationships:
- **Fact Tables:** `Sales Data`, `Returns Data`[cite: 2]
- **Dimension (Lookup) Tables:** `Calendar Lookup`, `Customer Lookup`, `Product Lookup`, `Categories Lookup`, `Subcategories Lookup`, `Territory Lookup`[cite: 2]

---

## Tech Stack & Advanced Techniques
- **Power BI Desktop:** Multi-page report design, custom report tooltips, and conditional formatting[cite: 3, 6].
- **Field & Numeric Parameters:** Implemented `Metric Parameter` and `Price Parameter` for dynamic visual switching and price simulation[cite: 4].
- **DAX (Data Analysis Expressions):** Dedicated `Mesure List` and `Customer Metric` tables housing time-intelligence, target comparisons, adjusted profit, and return rate measures[cite: 3, 4].
- **Power Query (M):** Data cleansing, transformation, and lookup table structuring.

---
---

# Maven Market Business Performance Analysis

## Executive Overview
The **Maven Market** project is an end-to-end business intelligence solution designed to analyze customer demographics, product categories, and regional store operations[cite: 1]. Built using **Power BI**, this interactive dashboard transforms raw transactional data into actionable insights to drive revenue growth, optimize store inventory, and enhance profitability[cite: 1].

---

## 📸 Dashboard Screenshots
![Maven Market Dashboard](./Mavien%20Market.webp) 

---

## Report Structure & Key Insights

### Customer Demographics
Focuses on identifying high-value customer segments and evaluating purchasing behavior[cite: 1].
- **Key Metrics:** Total Customers, Active Customer Rate, Average Revenue per Customer[cite: 1].
- **Visuals:** Income & occupation distributions, customer geographic mapping (USA, Mexico, Canada), and marital/gender breakdowns[cite: 1].
- **Technical Highlights:** Dynamic slicers and custom hierarchies (`Country > State > City`) for intuitive drill-down exploration[cite: 1].

### Store & Product Operations
Evaluates product profitability and physical store efficiency to streamline operational decisions[cite: 1].
- **Key Metrics:** Total Transactions, Quantity Sold, Return Rates, Margin per Product[cite: 1].
- **Visuals:** Matrix of Revenue/Cost/Profit by Category, Store Performance Treemap, Top 10 Dynamic Product Rankings[cite: 1].
- **Technical Highlights:** Data integration with `Returns_Data` to compute actual return rates alongside sales performance[cite: 1].

### Financial Performance & Target Tracking
Tracks core financial metrics against targets and historical benchmarks[cite: 1].
- **Key Metrics:** Total Revenue, Total Cost, Net Profit, MoM (Month-over-Month) Growth Rate[cite: 1].
- **Visuals:** Executive KPI Cards with trend indicators, Revenue Trend Line with forecasting, Regional Filters[cite: 1].
- **Technical Highlights:** Time-Intelligence DAX functions (`DATEADD`, `SAMEPERIODLASTYEAR`) for historical evaluation[cite: 1].

---

## Data Architecture & Modeling

The project utilizes a **Star Schema** to ensure fast query execution and optimal dynamic filtering across all visuals[cite: 1].

- **Fact Tables:** `Sales_Data`, `Returns_Data`[cite: 1]
- **Dimension Tables:** `Customers`, `Products`, `Stores`, `Calendar`[cite: 1]
- **Relationships:** $1:*$ (One-to-Many) single-direction filtering for data integrity[cite: 1].

---

## Tech Stack & Advanced Techniques

- **Power BI Desktop:** Core tool for visualization and dashboard delivery[cite: 1].
- **Power Query (M):** Data cleaning, unpivoting, column merging, and data type transformations[cite: 1].
- **DAX (Data Analysis Expressions):** Advanced calculated columns and measures using iterators (`SUMX`) and time intelligence[cite: 1].

---
---

# Item Sales Summary Report 

## Project Overview
The **Item Sales Summary** project is a comprehensive multi-page Power BI report designed to analyze product sales, profitability, and operational volume[cite: 1]. It provides executive-level KPIs alongside deep granular insights across various geographic states, years, and item categories[cite: 1].

---

## 📸 Dashboard Screenshots

### 1️⃣ Sales & Profitability Overview
![Sales & Profitability Overview](./Item%20Sales%20Summary%20.png)

### 2️⃣ Volume & Item Distribution
![Volume & Item Distribution](./Sales%20summary%20report.png)

### 3️⃣ Detailed Financial Breakdown by State
![Detailed Financial Breakdown](./Sales%20By%20State%20.png)

---

## Report Structure & Pages

1. **Sales & Profitability Overview (`Item Sales Summary.png`)**
   - High-level executive KPIs: **Total Sales ($20M)**, **Total Profit ($9.92M)**, **Cost ($9.96M)**, and **Profitability Margin (49.9%)**[cite: 1].
   - Multi-year trend analysis for total profit and tax-excluded figures (2013–2016)[cite: 1].
   - Regional breakdown of performance by states and top-performing stock items[cite: 1].

2. **Volume & Item Distribution (`Sales summary report.png`)**
   - Operational metrics tracking **Total Quantity (1M)**, split between **Chiller Items (14K)** and **Dry Items (1M)**[cite: 1].
   - Total sales trajectory across years alongside top item volumes[cite: 1].
   - Categorized state breakdown based on performance ratings (Amazing, Average, Poor)[cite: 1].

3. **Detailed Financial Breakdown (`Sales By State.png`)**
   - Granular table analysis detailing **Total Sales**, **Total Cost**, **Total Quantity**, and **Total Profit** across individual cities and states from 2013 to 2015[cite: 1].

---

## Key Features
- **Multi-Page Navigation:** Distinct reporting pages for Executive Summary, Product Volume, and Granular Details[cite: 1].
- **Interactive Filtering Pane:** Slice all pages dynamically by Employee, Customer, City, Buying Group, and Sales Territory[cite: 1].
- **Performance Tiering:** Automated classification of states and regions into operational performance groups (e.g., Amazing, Average, Poor)[cite: 1].

---

## Tools & Technologies Used
- **Power BI Desktop:** Multi-page interactive dashboard design and DAX calculations.
- **Power Query (M):** Data cleaning, modeling, and transformation.

    ---

## Report Structure & Pages

# Item Sales Summary Report 
### 1️⃣ Sales & Profitability Overview
![Sales & Profitability Overview](./Item%20Sales%20Summary%20.png)

### 2️⃣ Volume & Item Distribution
![Volume & Item Distribution](./Sales%20summary%20report.png)

### 3️⃣ Detailed Financial Breakdown by State
![Detailed Financial Breakdown](./Sales%20By%20State%20.png)

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
