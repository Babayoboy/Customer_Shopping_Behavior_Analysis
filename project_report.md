# Customer Shopping Behavior Analysis — Project Report

---

## Overview

This project analyzes customer shopping behavior using a structured three-phase workflow: data cleaning and preparation in Python, data exploration and querying in SQL, and interactive visualization in Power BI Desktop.

---

## Phase 1 — Data Cleaning & Preparation (`cleaning_prep.ipynb`)

The first phase focused on preparing the raw dataset for reliable downstream analysis. Using Python in a Jupyter Notebook, the following steps were carried out:

- **Loaded** the raw CSV dataset (`customer_shopping_behavior.csv`) containing customer demographics, purchase details, and behavioral metrics such as Review Rating, Subscription Status, Shipping Type, Discount Usage, and Previous Purchases.
- **Inspected** the dataset for shape, data types, and null values.
- **Handled missing values** to ensure no incomplete records would skew analysis results.
- **Standardized formats** across columns (e.g., consistent casing, correct data types).
- **Engineered new features**, most notably an `age_group` column, to enable age-based segmentation used in both the SQL queries and the Power BI dashboard.
- **Exported** the cleaned dataset ready for SQL import and BI visualization.

---

## Phase 2 — SQL Analysis (`Data_views.sql`)

The second phase used SQL to answer ten targeted business questions against the cleaned dataset.

| # | Business Question | Technique Used |
|---|---|---|
| 1 | Total revenue by gender | `GROUP BY` with `SUM` |
| 2 | Discount users who still spent above average | Subquery with `AVG` |
| 3 | Top 5 products by review rating | `ORDER BY` with `LIMIT` |
| 4 | Average purchase amount: Standard vs. Express Shipping | Conditional `WHERE` with `AVG` |
| 5 | Do subscribers spend more? (avg spend & total revenue) | `GROUP BY` with `AVG` and `SUM` |
| 6 | Products with highest discount usage percentage | `CASE WHEN` aggregation |
| 7 | Customer segmentation: New / Returning / Loyal | CTE with `CASE WHEN` |
| 8 | Top 3 most purchased products per category | CTE with `ROW_NUMBER()` window function |
| 9 | Repeat buyers (>5 purchases) vs. subscription status | Filtered `GROUP BY` |
| 10 | Revenue contribution by age group | `GROUP BY` with `SUM`, `ORDER BY` |

---

## Phase 3 — Power BI Dashboard (`Customer_Behavior_DashBoard.pbix`)

The final phase translated the analytical findings into an interactive Power BI dashboard titled **"Customer Behavior Dashboard"**.

### Key Metrics (KPI Cards)
| Metric | Value |
|---|---|
| Number of Customers | 3.9K |
| Average Purchase Amount | $59.8 |
| Average Review Rating | 3.8 |

### Visuals Included

- **Customers by Subscription Status** *(Donut Chart)* — 73% (2.85K) non-subscribers vs. 27% (1.05K) subscribers.
- **Revenue by Category** *(Bar Chart)* — Clothing leads at ~100K, followed by Accessories, Footwear, and Outerwear.
- **Sales by Category** *(Bar Chart)* — Clothing again dominates with ~1,750 sales units.
- **Revenue by Age Group** *(Horizontal Bar Chart)* — Young and Middle-age groups generate the highest revenue (~60K each), followed by Adult and Senior.
- **Sales by Age Group** *(Horizontal Bar Chart)* — Young customers lead in transaction count (~1,000), followed by Middle-age, Senior, and Adult.

### Slicers / Filters
The dashboard includes interactive filters for:
- **Subscription Status** (Yes / No)
- **Gender** (Female / Male)
- **Category** (Accessories, Clothing, Footwear, Outerwear)
- **Shipping Type** (2-Day, Express, Free Shipping, Next Day Air, Standard, Store Pickup)

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Python (Jupyter Notebook) | Data cleaning & feature engineering |
| SQL (PostgreSQL / SQLite) | Data querying & business insight extraction |
| Power BI Desktop | Interactive dashboard & visualization |

---

## Files

| File | Description |
|---|---|
| `dataset/customer_shopping_behavior.csv` | Raw source dataset |
| `cleaning_prep.ipynb` | Data cleaning & preparation notebook |
| `Data_views.sql` | SQL queries for business analysis |
| `Customer_Behavior_DashBoard.pbix` | Power BI interactive dashboard |
