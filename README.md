# Sales Analytics Dashboard - Power BI

An interactive business intelligence solution designed to monitor, analyze, and visualize e-commerce sales performance, transactional trends, and regional fulfillment metrics.

---

## 📋 Table of Contents

* Project Overview
* Key Features & Dashboard Capabilities
* Data Model & Architecture
* DAX Measures & Calculations
* Key Business Insights
* Project Structure
* Getting Started
* Author

---

## 🚀 Project Overview

The **Sales Analytics Dashboard** is built using Power BI to empower stakeholders with actionable insights into retail and e-commerce operations. By transforming raw transactional logs into dynamic visual reports, this dashboard enables leadership and operations teams to track revenue growth, identify top-performing product categories, evaluate regional fulfillment efficiency, and monitor order status breakdowns in real time.

---

## 📊 Key Features & Dashboard Capabilities

* **Executive Summary / KPI Cards:** High-level tracking of Total Revenue, Total Orders, Average Order Value (AOV), and Total Quantity Sold.
* **Monthly & Yearly Trend Analysis:** Time-series line and bar charts illustrating sales growth trajectories and seasonal purchasing patterns.
* **Category & Product Performance:** Granular breakdowns of revenue contribution by product category and sub-category.
* **Regional & Fulfillment Analytics:** Geographic distribution of sales combined with fulfillment status metrics (delivered, pending, canceled, returned).
* **Interactive Slicers & Filters:** Dynamic filtering options by date ranges, regions, and customer segments to drill down into specific data points.

---

## 🗄️ Data Model & Architecture

* **Data Sources:** Cleaned and transformed relational datasets (CSV/Excel/SQL backend).
* **Schema Design:** Star Schema featuring a central Fact Table (Transactions/Sales) connected to supporting Dimension Tables (`Dim_Date`, `Dim_Customer`, `Dim_Product`, `Dim_Region`).
* **Relationships:** One-to-Many ($1:N$) relationships established between dimension primary keys and fact table foreign keys to ensure high query performance and accurate cross-filtering.

---

## 🧮 DAX Measures & Calculations

Core analytical metrics implemented using Data Analysis Expressions (DAX):

```dax
-- Total Sales Revenue
Total Sales = SUM(Sales[SalesAmount])

-- Total Order Volume
Total Orders = DISTINCTCOUNT(Sales[OrderID])

-- Average Order Value
Average Order Value = DIVIDE([Total Sales], [Total Orders], 0)

-- Year-over-Year (YoY) Sales Growth
Sales YoY % = 
DIVIDE(
    [Total Sales] - CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Dim_Date'[Date])),
    CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Dim_Date'[Date])),
    0
)

```

---

## 💡 Key Business Insights

1. **Revenue Concentration:** Top-performing product categories drive over 60% of total revenue, highlighting key drivers for inventory stocking.
2. **Fulfillment Bottlenecks:** Tracking order status highlights regional fulfillment delays, enabling targeted operational improvements.
3. **Seasonal Trends:** Clear sales surges observed during festive and promotional periods, informing future marketing campaign planning.

---

## 📂 Project Structure

```text
Sales-Analytics-Dashboard--POWER-BI/
│
├── Sales analytics dashboard power bi/    # Power BI .pbix file and supporting datasets
├── LICENSE                                # MIT License file
└── README.md                              # Project documentation

```

---

## 🛠️ Getting Started

### Prerequisites

* [Power BI Desktop](https://powerbi.microsoft.com/desktop/) installed on your machine.

### Installation & Usage

1. **Clone the repository:**
```bash
git clone https://github.com/nikki-analytics/Sales-Analytics-Dashboard--POWER-BI.git

```


2. **Open the project:**
Navigate to the cloned folder and open the `.pbix` file using Power BI Desktop.
3. **Refresh Data:**
Update the data source path if necessary to point to your local data files, then click **Refresh** to load the dashboard.

---

## 👤 Author

**Nikki Hela**

* Data Operations & Analytics Professional
* GitHub: [@nikki-analytics](https://github.com/nikki-analytics)
