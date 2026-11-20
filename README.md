# 📊 Sales Performance Analytics Dashboard | Power BI

### Interactive Sales, Profitability, Product & Customer Analytics

Interactive Power BI Sales Analytics Dashboard featuring revenue analysis, profitability, customer segmentation, product performance, time intelligence, and dynamic DAX-driven business insights.

## 📌 Project Overview

This project is an interactive **Sales Performance Analytics Dashboard** developed using **Microsoft Power BI**.

The dashboard analyzes sales revenue, profitability, product performance, customer segments, sales channels, and geographical trends to support data-driven business decisions.

It consists of **3 interactive report pages**, featuring DAX-based KPIs, time intelligence calculations, synchronized slicers, and dynamic business insights.

The main goal is to transform raw sales data into meaningful, actionable business insights.

---

## 🎯 Project Objectives

- Analyze overall sales revenue, gross profit, and profit margins.
- Monitor monthly revenue trends and growth.
- Identify top-performing products and categories.
- Compare sales performance across countries and sales channels.
- Analyze customer segments and their revenue contributions.
- Evaluate product discounts and profitability.
- Generate dynamic business insights and recommendations.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Power BI Desktop | Dashboard development and visualization |
| Power Query | Data cleaning and transformation |
| DAX | KPI calculations and dynamic business insights |
| Data Modeling | Calendar table and relationships |
| Power BI Slicers | Interactive filtering across report pages |

---

## 📊 Key Performance Indicators

| KPI | Value |
|-----|------:|
| Total Revenue | 645.22K |
| Total Gross Profit | 296.38K |
| Total COGS | 348.84K |
| Gross Margin | 45.94% |
| Total Orders | 2,707 |
| Average Order Value | 238.35 |
| Total Quantity Sold | ~7K |
| Revenue Per Unit | 96.33 |
| Weighted Discount | 6.48% |
| Profit Per Order | 109.49 |

> **Note:** These values represent the overall dataset with filters cleared. Metrics update dynamically when slicers are applied.

---

# 📈 Dashboard Overview

## 1️⃣ Sales Performance Overview

This page provides a high-level overview of overall business performance.

### Key Features
- Total Revenue, Gross Profit, Gross Margin, AOV, and Total Orders
- Profit Contribution by Product Category
- Revenue Contribution by Sales Channel
- Revenue vs COGS by Product Category
- Monthly Revenue and Gross Profit Trends
- Gross Margin by Product Category
- Top 10 Countries by Revenue

### 📷 Dashboard Preview

<img width="1335" height="751" alt="Screenshot 2026-11-20 124058" src="https://github.com/user-attachments/assets/bc1dd198-5b5f-4658-acbb-ccc27c66600a" />

### Business Value

Helps stakeholders understand overall financial performance, revenue distribution, product category profitability, and key sales trends.

---

## 2️⃣ Sales Performance Insights

This page provides deeper analysis of sales growth, geographical performance, and product-level revenue.

### Key Features
- Total COGS and Profit Per Order
- Month-over-Month Revenue Growth
- Gross Profit Growth
- Sales Channel Revenue vs Gross Profit
- Country Revenue vs Gross Profit
- Monthly Revenue Growth Trends
- Top 5 Products by Revenue
- Interactive Revenue, Profit, and Orders Selector
- Country-wise Revenue Map

### 📷 Dashboard Preview

<img width="670" height="374" alt="Insight" src="https://github.com/user-attachments/assets/99cfce51-9c3e-4c8a-8b10-e8786ac065dc" />

### Business Value

Helps identify sales growth opportunities, compare regional profitability, evaluate sales channels, and understand monthly revenue fluctuations.

---

## 3️⃣ Product & Customer Analysis

This page focuses on product profitability, customer segments, discount analysis, and dynamic business recommendations.

### Key Features
- Total Quantity Sold
- Revenue Per Unit
- Weighted Discount Percentage
- Product Revenue vs Gross Margin
- Discount Amount by Product Category
- Customer Type Revenue vs Gross Profit
- Top 10 Products by Gross Profit
- Total Orders by Customer Type
- Product Category × Customer Type Matrix
- Dynamic Business Insights & Recommendations

### 📷 Dashboard Preview

<img width="669" height="377" alt="P   C" src="https://github.com/user-attachments/assets/d7f25fa4-04a1-49ec-b05e-bfdde42377ac" />

### Business Value

Helps identify profitable products, understand customer segment contributions, monitor discount exposure, and support product and pricing decisions.

---

# 💡 Key Business Insights & Recommendations

The dashboard includes **5 dynamic DAX-driven business insights** that automatically update according to the selected filters.

### 1. Financial Performance

**Finding:**
- Total Revenue: 645.22K
- Total Gross Profit: 296.38K
- Gross Margin: 45.94%

**Recommendation:**
Monitor operational costs and product profitability to maintain healthy margins.

### 2. Product Category Profitability

**Finding:**
- Camping generates the highest category revenue at approximately 198.5K.
- Camping also has the lowest gross margin among product categories.

**Recommendation:**
Review Camping product costs, pricing, and discount strategies to improve profitability.

### 3. Monthly Revenue Growth

**Finding:**
- November 2026 recorded 33.32% revenue growth.
- December 2026 recorded a 22.12% revenue decline.

**Recommendation:**
Investigate seasonal demand, product performance, and sales channel contributions to understand the year-end decline.

### 4. Customer Segment Performance

**Finding:**
- Returning customers generate approximately 226.1K in revenue.
- They contribute approximately 104.5K in gross profit.

**Recommendation:**
Strengthen customer engagement and retention strategies while exploring growth opportunities in other segments.

### 5. Product Profitability

**Finding:**
- Summit Backpack 45L generates approximately 64.9K in revenue.
- It contributes approximately 29.6K in gross profit.

**Recommendation:**
Prioritize high-performing products and monitor demand to support inventory and sales planning.

> **Note:** These findings represent the unfiltered dataset. The dashboard's dynamic insights update automatically based on slicer selections.

---

# 🧮 Key DAX Measures

DAX was used to calculate financial KPIs, time intelligence metrics, and dynamic business insights.

### Total Revenue

```dax
Total Revenue =
SUM(SalesDataTable[Revenue])
```

### Total Gross Profit

```dax
Total Gross Profit =
SUM(SalesDataTable[Gross Profit])
```

### Gross Margin

```dax
Gross Margin =
DIVIDE(
    [Total Gross Profit],
    [Total Revenue],
    0
)
```

### Total Orders

```dax
Total Orders =
DISTINCTCOUNT(SalesDataTable[ID])
```

### Average Order Value

```dax
Average Order Value (AOV) =
DIVIDE(
    [Total Revenue],
    [Total Orders],
    0
)
```

### Previous Month Revenue

```dax
Previous Month Revenue =
CALCULATE(
    [Total Revenue],
    DATEADD(
        Calendar_Table[Date],
        -1,
        MONTH
    )
)
```

### Revenue Growth %

```dax
Revenue Growth % =
DIVIDE(
    [Total Revenue] - [Previous Month Revenue],
    [Previous Month Revenue],
    0
)
```

### Total Quantity

```dax
Total Quantity =
SUM(SalesDataTable[Units Sold])
```

### Revenue Per Unit

```dax
Revenue Per Unit =
DIVIDE(
    [Total Revenue],
    [Total Quantity],
    0
)
```

### Weighted Discount %

```dax
Weighted Discount % =
DIVIDE(
    [Total Discount Amount],
    SUMX(
        SalesDataTable,
        SalesDataTable[Unit Price]
            * SalesDataTable[Units Sold]
    ),
    0
)
```

Additional DAX measures were created for:

- Gross Profit Growth
- Profit Per Order
- Latest Monthly Revenue Growth
- Financial Performance Insights
- Category Performance Insights
- Customer Segment Insights
- Product Profitability Insights

---

# ✨ Dashboard Features

## 🔹 Interactive & Synchronized Slicers

Users can filter the dashboard by:

- Year
- Month
- Quarter
- Country
- Product Category
- Sales Channel

Slicers are synchronized across all three pages to provide consistent analysis.

## 🔹 Dynamic Business Insights

The dashboard includes five DAX-driven insights that automatically respond to user selections.

These insights help identify:
- Financial performance
- Category profitability opportunities
- Monthly revenue growth or decline
- Leading customer segments
- Top-performing products

## 🔹 Interactive Data Visualization

The report includes:

- KPI Cards
- Donut Charts
- Bar and Column Charts
- Line Charts
- Scatter Plots
- Matrix Visuals
- Geographical Map
- Interactive Metric Selector

---

# 🔍 Data Validation

The following checks were performed to improve calculation accuracy:

- Revenue, COGS, and Gross Profit reconciliation
- Distinct order count verification
- Customer segment order total validation
- Total quantity calculation verification
- Revenue per unit calculation verification
- Weighted discount measure review
- Revenue growth DAX validation
- Cross-page slicer synchronization testing

---

# 📁 Project Structure

```text
Sales-Performance-Analytics-PowerBI/
│
├── README.md
│
├── Sales_Performance_Dashboard.pbix
│
├── Dataset/
│   └── sales_data.xlsx
│
└── Screenshots/
    ├── Sales_Performance_Overview.png
    ├── Sales_Performance_Insights.png
    └── Product_Customer_Analysis.png
```

*The structure above is suggested. Include the dataset only if it can be shared.*

---

# 🚀 How to Use

1. Clone or download this repository.
2. Open the `.pbix` file using Microsoft Power BI Desktop.
3. Update the dataset source path if required.
4. Navigate between the three dashboard pages.
5. Apply slicers to analyze different business dimensions.
6. Explore the charts and dynamic business recommendations.

---

# 📚 Skills Demonstrated

- Power BI Dashboard Development
- Power Query
- Data Modeling
- DAX & Time Intelligence
- KPI Development
- Sales Performance Analysis
- Product Profitability Analysis
- Customer Segmentation
- Data Validation
- Interactive Dashboard Design
- Business Insights & Data Storytelling

---

# 🏁 Conclusion

This project demonstrates how Power BI can transform sales data into an interactive and insightful business intelligence solution.

By combining financial KPIs, monthly trends, product analysis, customer segmentation, geographical performance, and dynamic DAX-driven recommendations, the dashboard supports informed business decisions.

The project highlights practical experience in **Power BI, DAX, data modeling, business analysis, and data storytelling**.

---

⭐ **If you find this project useful, consider starring the repository!**
