# Executive-Revenue-monitoring-dashboard-for-Ecommerce-company
A comprehensive Tableau BI dashboard to deliver clear business insights. With executive-level financial performance tracking, user monetization metrics, and period-over-period revenue decomposition analysis to identify key revenue drivers.
---

## 📌 Executive Summary

This analytics dashboard provides business executives, product managers, and data analysts with an overview of the key financial metrics and drivers of the company. It is split into three primary views:

1. **Executive Metrics Dashboard**: Tracks latest trend of core SaaS/E-commerce KPIs: revenue, customer lifetime value (LTV), paying user trends, and average revenue per user (ARPU). 
2. **Revenue drivers decomposition & Period Comparison Analysis**: Deconstructs daily revenue flows across available demographic and categorical dimensions (e.g., Age Group, Gender, Location, Product Category) and performs dynamic period-over-period variance analysis to identify key drivers of revenue change for executive decisions.
3. **Customer Insights at a Glance**: Empowers product owners to make data-driven decisions. This dashboard delivers immediate clarity on revenue distribution by geography and product category, isolates dominant age-gender segments, and tracks monthly year-over-year seasonality trends.

---

## 📊 Dashboard Views & Architecture

### 1. Key Performance Indicators (KPIs) Trends

Your business pulse in one place. Monitor your primary North-Star metrics alongside real-time trend analysis and performance health checks:
<img width="1706" height="894" alt="image" src="https://github.com/user-attachments/assets/03b65a4b-1b9b-4d9f-ab04-902fbf3253b8" />
<!--
| Metric | Current Value | W-o-W % Change | Baseline | Description |
| :--- | :---: | :---: | :---: | :--- |
| **Total Revenue** | **$1,304K** | 🔻 -2.7% | $89K Daily Avg | Total net cumulative revenue across the monitored timeframe with historical trends and short-term projected growth path. |
| **Average LTV** | **3.3K** | 🔻 -10.4% | ~3K Customer LTV | Average Lifetime Value per customer, detailing historical volatility and forecasted trajectory. |
| **Daily Paying Users** | **28** | 🔻 -7.9% | 30 Customers Avg | Daily active paying customer count, tracking retention dips and projected conversion recovery. |
| **ARPU (Avg Revenue Per User)**| **3,413** | 🟢 +6.9% | $3.0K Baseline | Average Revenue Per User, showing consistent upward momentum despite user count contraction. |-->

#### Key Visual Features:
* **Historical vs. Current Breakdown**: Blue solid lines represent actual historical performance; orange lines display latest trends.
* **Baseline Threshold Alignment**: Horizontal dashed red reference lines indicate historical mean baselines.
* **Percentage change callout**: Clear visual indicator highlighting the latest percentage growth or decline.
  
#### Data Constraint:
* **Missing DAU Metric**: Daily Active User (DAU) data is unavailable in this dataset, preventing the calculation of a daily conversion rate. While daily conversion is the preferred KPI for evaluating sales performance, Average customer LTV was chosen for this analysis. 
---

### 2. Revenue drivers decomposition analysis

The second view enables granular root-cause analysis of revenue shifts between customizable comparative windows.
<img width="1920" height="1080" alt="Recording 2026-08-16 at 15 44 44" src="https://github.com/user-attachments/assets/7e10493e-0761-4ae9-a014-02f5fb6d9528" />

#### Interactive Controls & Parameters:
* **Dimension Selector (`Colour by`)**: Dynamic slicing by available demographic and categorical dimensions (*Product category*, *Age group*, *Gender*, or *Location*).
* **Date Range Filter**: Date range slider for available date range.
* **Period Comparison Controls**:
  * **Period 1 Range**: Baseline period.
  * **Period 2 Range**: Target period.

#### Dynamic Visual Analysis Panels:
1. **Stacked Daily Revenue Bar Chart**: Visualizes day-over-day net revenue trend stacked by user selected dimension (e.g., Product category/ Age groups), highlighting structural shifts across Baseline and Target windows.
2. **Top Contributors to Change Breakdown**: Dimensions are ranked in descending order by their impact on overall trend to surface the strongest revenue drivers.
   * **Avg daily revenue**:
      - Horizontal bars: Baseline period average revenue for each dimension.
      - Vertical reference line: Target period average revenue for each dimension.
      - Delta Label: Absolute numeric change between the selected periods.
   * **Period Percentage Difference**: Relative percentage difference between target and baseline periods, pinpointing dimensions with the highest growth or decline.
   * **Percentage Contribution to Change**: Share of total net variance attributable to each dimension, identifying the key primary revenue driver(s).

---

### 3. Customer Insights at a Glance

This dashboard delivers immediate clarity on revenue distribution by geography and product category, isolates dominant age-gender segments, and tracks monthly year-over-year seasonality trends — giving business owners a comprehensive, visual profile of their customer base.

<img width="1676" height="878" alt="image" src="https://github.com/user-attachments/assets/747a99b2-585f-4aed-9098-8b086ecd9eed" />

#### Key Business Insights derived from the Dashboards:
* **Revenue Share by Location (Treemap)**: Highlights top geographic revenue generators led by **Delhi (20%)**, **Mumbai (19%)** and **Bangalore (15%)** which together account for over half of total revenue. <br>Recommended next step: cross-check with regional managers to confirm if these proportions align with expectations or signal local underperformance.
* **Revenue Share by Product Category (Horizontal Bar Chart)**: Ranks core catalog segments by net revenue volume. **Electronics** dominates with **32%** of total revenue, followed by **Clothing (18%)** and **Beauty and Health (16%)**. <br>Recommended next step: collaborate with procurement to incorporate unit cost data and calculate true profit margins — a more actionable business metric.
* **Monthly Revenue Seasonality (Multi-Year Line Chart)**: Tracks historical monthly revenue patterns, revealing predictable seasonal peaks during the Q4 holiday season (Oct–Dec) and mid year dips (Jun - Jul). <br>Recommended next step: partner with marketing and sales to run targeted promotions during low-performing months (Jun & Jul) to smooth out seasonal troughs.
* **Revenue Share by Gender and Age Group (Population Pyramid / Demographic Grid)**: Breaks down spend share across Gender and Age Groups. Revenue heavily concentrates in the 25–45 cohort (14% Female, 12% Male, 14% Other) and the 18–25 cohort (11% Female, 10% Male, 9% Other). <br>Recommended next step: align performance marketing and product design with the core 18–45 demographic, while testing targeted campaigns to unlock underpenetrated segments like the 45+ age group.

## 🛠️ Data Pipeline & Technology Stack

* **BI Platform**: Tableau Desktop
* **Data Sources**:
  * **Dataset Name**: E-Commerce Dataset for Data Analysis
  * **URL**: [Kaggle Dataset: ecommerce-dataset-for-data-analysis](https://www.kaggle.com/datasets/shrishtimanja/ecommerce-dataset-for-data-analysis)
  * **Author**: Shrishti Manja
* **Calculated Fields & Metrics**:
  * **ARPU**: `SUM([Net Revenue]) / COUNTD([Paying User ID])`
  * **LTV**: `SUM([Cumulative Revenue per customer]) / COUNTD([Total Unique Customers])`
  * **Period Variance**: `AVG(Period 2 Revenue) - AVG(Period 1 Revenue)`
  * **% Contribution**: `(Cohort Variance / Total Revenue Variance) * 100`

---
