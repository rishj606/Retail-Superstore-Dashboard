# Retail Superstore Dashboard

[![Power BI](https://img.shields.io/badge/Power_BI-EFD24C?style=for-the-badge&logo=PowerBI&logoColor=white)](https://powerbi.microsoft.com/)
[![PL-300](https://img.shields.io/badge/PL--300-Cert-00B4F0?style=for-the-badge&logo=microsoft)](https://learn.microsoft.com/en-us/credentials/certifications/power-bi-data-analyst/)

**End-to-end Power BI retail analytics project using [Kaggle Superstore dataset](https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting) (9.8k orders). Demonstrates data preparation, semantic modeling, time-intelligence DAX, and polished report UX for PL-300 skills validation.**

---

## Project Goal
Build a CV/portfolio-ready Power BI dashboard showcasing:
- Clean data transformation (Power Query)
- Proper semantic modeling (Date table, relationships)
- Advanced time-intelligence measures (YoY, MoM, YTD, Rolling 12M)
- Professional report design (interactive slicers, conditional formatting, decomposition analysis)

**Note**: This dataset contains sales data only (no profit/cost/quantity). The focus is demonstrating **time-intelligence** and **dimensional analysis**, not full P&L modeling.

---

## V1: Data Preparation (2026-01-14)
- Downloaded Rohit Sahoo's Superstore CSV from Kaggle.
- Power Query ETL: Removed Row ID, Order/Product ID, Postal Code, Country (identifier/static noise).
- Data types: Dates parsed, Sales as Decimal.
- Result: Clean 9.8k-row fact table ready for modeling.

![V1 Fields](screenshots/screenshots-v1-cleaning.png)

## Tech Stack
- Power BI Desktop (latest)
- Power Query (M language)

## Quick Start
1. Download [Retail-Superstore-Dashboard-V3.pbix](Retail-Superstore-Dashboard-V3.pbix)
2. Open in Power BI Desktop
3. Navigate through the 4 report pages to see the interactive visuals.

---

## V2: Semantic Model + Time Intelligence Measures (2026-01-17)
V2 focuses on building a reusable semantic model and implementing validated time-intelligence measures. Report pages in V2 are for measure validation only.

### Date Dimension and Relationships
- Created a dedicated `'Date'` table and marked it as the model Date table.
- Established relationship: `'Date'[Date]` (1) → `train[Order Date]` (*).
- Added `YearMonth` (text) and `YearMonth Sort` (numeric) columns for chronological sorting.

![V2 Date Relationship](screenshots/screenshots-v2-daterelationship.png)

### Measures Implemented (V2)
**Time Intelligence** (monthly grain, driven by `'Date'` table):
- `Total Sales`, `Sales Prev Month`, `Sales Growth MoM %`, `Sales MoM Δ`
- `Sales LY` (Last Year), `Sales Growth YoY %`, `Sales YoY Δ`
- `Sales YTD`, `Sales Rolling 12M` (Trailing Twelve Months)

**Product Analysis**:
- `Sales Rank (Product)` (Top-N ready with RANKX)
- `Sales % of Total (Product)` (uses REMOVEFILTERS)

### Measure Validation (V2)
Validation pages created to confirm calculations at time and product grain.

![V2 Time Validation](screenshots/screenshot-v2-MeasureValidation.png)
![V2 Product Validation](screenshots/screenshot-v2-MeasureValidation2.png)

**Manual Checks Performed**:
- MoM: Apr 2015 (27.9K) → May 2015 (23.6K) = -15.27% ✓
- YoY: 2015 total (479.9K) vs 2016 total (459.4K) = -4.26% ✓

---

## V3: Polished Report UX with Interactive Visuals (2026-01-27)
V3 delivers a CV-ready, minimalistic report with 4 interactive pages demonstrating time-intelligence in action.

### Design Principles
- **Minimalist aesthetic**: Light gray canvas, white cards, consistent blue accent (#1976D2).
- **Synced slicers**: Year, Region, Segment filters apply consistently across pages.
- **Grid alignment**: Pixel-perfect layout for professional appearance.

### Page 1: Executive Overview
High-level KPIs and trends for executive-level insights.

**Visuals**:
- **5 KPI Cards**: Total Sales, Sales YTD, Sales LY, YoY Δ, YoY Growth %
- **Main Trend (Line Chart)**: Monthly sales (Current vs Last Year)
- **MoM Variance (Column Chart)**: Month-over-month change with conditional colors
- **Rolling 12M Trend (Line Chart)**: Smoothed long-term pattern

![Executive Overview](screenshots/screenshot-v3-page1-executive-overview.png)

**Interactive Example** (Year = 2016):
![Executive Overview Filtered](screenshots/screenshot-v3-page1-filtered-2016.png)

### Page 2: Product Performance
Deep-dive into product-level sales with ranking and contribution analysis.

**Visuals**:
- **Top 10 Products (Bar Chart)**: Visual-level filter (Top N by Total Sales)
- **Product Matrix**: Detailed table with Total Sales, Rank, % of Total, YoY Δ
- **Search Slicer**: Product Name dropdown with search enabled

![Product Performance](screenshots/screenshot-v3-page2-product-performance.png)

### Page 3: Region Performance
Geographic analysis with map visualization and state-level breakdown.

**Visuals**:
- **Sales by State (Bubble Map)**: Hero visual with size = Total Sales
- **Sales by Region (Bar Chart)**: High-level regional comparison
- **State Performance Matrix**: Detailed state metrics (Total Sales, LY, YoY Δ, YoY %)

![Region Performance](screenshots/screenshot-v3-page3-region-performance.png)

### Page 4: Key Performance Drivers
Root-cause analysis using AI-powered Decomposition Tree.

**Visual**:
- **Decomposition Tree**: Analyze `Sales YoY Δ` by Region → State → Segment → Category → Product
- Users can click "+" to drill into drivers and use "High Value/Low Value" AI suggestions

![Drivers](screenshots/screenshot-v3-page4-drivers.png)

---


## License
Data: [Kaggle Superstore Dataset](https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting) by Rohit Sahoo (CC BY-NC-SA 4.0)  
Code/Report: MIT License

---

**Author**: [rishj606](https://github.com/rishj606)  
