# Maven Roasters : Coffee Shop Sales Analysis

> An end-to-end Excel analytics project covering data preparation, PivotTable analysis, and interactive dashboard design for a fictitious New York City coffee shop chain.

**Tool:** Microsoft Excel  
**Source:** [Maven Analytics Guided Project](https://app.mavenanalytics.io/guided-projects/72ec0a0d-bc7d-4ac4-a8da-da811f9061d6)  
**Dataset:** Coffee Shop Sales: Maven Roasters, NYC  
**Scope:** 149,116 transactions · 3 store locations · 11 fields

> **Disclaimer:** This is a portfolio project completed as part of a Maven Analytics guided project. The dataset is fictitious and does not represent the actual performance or operations of any real coffee shop or business.

---

## Project Overview

This project analyses transaction-level sales data from Maven Roasters, a fictitious multi-location coffee shop in New York City. Starting from a raw single-table dataset, the project covers data preparation, exploratory analysis via PivotTables, and the construction of a dynamic, slicer-driven Excel dashboard.

The analysis is structured around three objectives:

| Objective | Focus |
|-----------|-------|
| Data Preparation | Profiling, QA, and calculated fields |
| PivotTable Analysis | Time series, product trends, and category breakdown |
| Dashboard Design | Interactive visualisation with slicer-driven filtering |

---

## Repository Structure

```
├── Coffee_Shop_Sales.xlsx        # Working file - raw data, PivotTables, dashboard
├── README.md                     # This file
└── screenshots/
    ├── dashboard.png             # Final dashboard view
    ├── pivot_revenue_month.png   # Revenue by month PivotTable
    └── pivot_products.png        # Top 15 products PivotTable
```

---

## Objective 1 - Data Preparation

The raw dataset contained 149,116 transaction records across 11 fields covering transaction ID, date, time, store location, product details, unit price and quantity.

**Calculated fields added:**

| New Column | Formula Logic | Purpose |
|-----------|--------------|---------|
| `Revenue` | `unit_price * transaction_qty` | Enables revenue aggregation |
| `Month` | `TEXT(date, "mmm")` | Displays as Jan, Feb etc - sorts correctly via custom list |
| `Day of Week` | `TEXT(date, "ddd")` | Displays as Mon, Tue etc for readable trend charts |
| `Hour` | `HOUR(transaction_time)` | Extracts hour to identify peak trading windows |

**Design decision:** Month and Day of Week were stored as text labels rather than numbers - this improves chart readability for non-technical viewers but requires a custom sort order to prevent Excel defaulting to alphabetical (Apr before Jan). Custom lists were applied to enforce chronological ordering.

---

## Objective 2 - PivotTable Analysis

Five PivotTables were built on a dedicated analysis sheet to explore the data from different angles:

<!-- Paste screenshot of PivotTables here -->

**Revenue by Month**  
Shows the full-year revenue trajectory - used to identify seasonal peaks and dips across the three store locations.

**Transactions by Day of Week**  
Reveals which days drive the most footfall - critical for staffing and promotional planning.

**Transactions by Hour of Day**  
The most operationally useful view - identifies the morning rush window and any secondary peaks later in the day.

**Transactions by Product Category**  
Sorted descending by transaction count - shows which broad categories (Coffee, Tea, Bakery etc) drive volume vs which are niche.

**Top 15 Product Types by Transactions**  
Filtered to the top 15 - cuts noise from low-volume items and focuses attention on the products that actually move the business.

---

## Objective 3 - Interactive Dashboard

![Dashboard](Screenshots/Screenshot%202026-06-22%20010834.png)


The final dashboard consolidates all five analytical views into a single sheet with a store location slicer connected to all PivotTables simultaneously.

**Chart types used:**

| Visual | Chart Type | Why |
|--------|-----------|-----|
| Revenue by Month | Line chart | Shows trend direction clearly over time |
| Transactions by Day of Week | Column chart | Easy comparison across 7 categories |
| Transactions by Hour of Day | Column chart | Peak hour pattern is immediately visible |
| Transactions by Product Category | Bar chart | Horizontal bars handle longer category names cleanly |
| Top 15 Product Types | PivotTable (formatted) | Exact numbers matter here - a chart would lose precision |

**Dashboard design decisions:**
- Raw PivotTables hidden - only the charts and formatted table are visible to avoid clutter
- Worksheet gridlines removed - gives the dashboard a cleaner, more professional appearance
- Slicer connects all visuals simultaneously - filtering by store location updates every chart and table at once
- Consistent colour scheme applied across all charts - avoids the default Excel rainbow palette

---

## Key Findings

**On time patterns:**
- The morning rush is the dominant revenue window - transactions peak sharply between 7am and 10am and drop significantly after midday. Staffing, stock levels and promotional activity should be front-loaded to the morning.
- Weekday performance is strong and relatively consistent. Weekend patterns differ by location - a slicer-filtered view by store reveals location-specific behaviour worth acting on.

**On products:**
- Coffee dominates transaction volume as expected, but the category-level view reveals that Bakery and Tea hold meaningful share - these categories should not be treated as afterthoughts in menu planning or display.
- The Top 15 product view shows that a small number of SKUs drive the majority of transactions. Stock-out risk on these items has an outsized impact on revenue compared to any other product.

**On locations:**
- Filtering the dashboard by store location reveals material differences in product mix and peak hours between locations. A product that sells well at one location may underperform at another - location-level decisions should not be made from blended totals.

---

## Recommendations

**1. Protect the morning window**  
The hour-of-day chart makes clear that the business lives and dies by its morning performance. Staffing, stock replenishment, equipment readiness and promotional offers should all be optimised for the 7–10am window - not spread evenly across the day.

**2. Review underperforming locations individually**  
Blended totals mask location-level differences. Use the store slicer to run the full analysis per location before making any product range or operational decisions. What looks like a company-wide pattern may be driven entirely by one store.

**3. Protect the Top 5 products**  
A small number of product types generate a disproportionate share of transactions. Ensure these are always in stock, always prominently displayed, and never discounted without a clear reason - their volume makes any disruption costly.

**4. Investigate the revenue dip months**  
The monthly revenue line chart reveals periods of underperformance. Before attributing these to seasonality, check whether they correlate with operational changes, staffing issues, or external factors. Seasonality and operational problems can look identical in a chart.

**5. Use the day-of-week chart to guide staffing**  
If transaction volume drops materially on certain days, staff scheduling should reflect that - overstaffing slow days has a direct cost. The day-of-week chart gives the data needed to make that conversation with concrete numbers rather than intuition.

---

## Skills Demonstrated

| Skill | Detail |
|-------|--------|
| Excel data preparation | Calculated columns, TEXT formulas, HOUR extraction |
| PivotTable design | Multi-table layout, custom sorting, Top N filtering |
| PivotChart creation | Line, column and bar charts linked to PivotTables |
| Dashboard design | Slicer integration, gridline removal, layout and formatting |
| Analytical thinking | Findings framed as decisions, not just observations |

---

## How to Open

1. Download `Coffee_Shop_Sales.xlsx`
2. Open in **Microsoft Excel** (2016 or later recommended)
3. Navigate to the **Dashboard** sheet
4. Use the **Store Location slicer** to filter all visuals by location

---

*Maven Analytics Guided Project · Excel · Portfolio Submission*
