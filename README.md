# Retail Superstore Dashboard 🚀

[![Power BI](https://img.shields.io/badge/Power_BI-EFD24C?style=for-the-badge&logo=PowerBI&logoColor=white)](https://powerbi.microsoft.com/)
[![PL-300](https://img.shields.io/badge/PL--300-Cert-00B4F0?style=for-the-badge&logo=microsoft)](https://learn.microsoft.com/en-us/credentials/certifications/power-bi-data-analyst/)

**End-to-end Power BI retail analytics project using [Kaggle Superstore dataset](https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting) (9.8k orders). Progressive builds for PL-300 prep.**

## 📋 V1: Data Preparation (2026-01-14)
- Downloaded Rohit Sahoo's Superstore CSV.
- Power Query ETL: Removed Row ID, Order/Product ID, Postal Code, Country (identifier/static noise).
- Data types: Dates parsed, Sales/Profit as Decimal.
- Result: Clean 9.8k-row fact table ready for modeling.

![V1 Fields](screenshots-v1-cleaning.png)

## Tech Stack
- Power BI Desktop (latest)
- Power Query (M language)

## Upcoming
- V2: Date dimension, DAX KPIs (Total Sales, Profit Margin)
- V3: Interactive visuals, maps, slicers

## Quick Start
1. Download [V1.pbix](Retail-Superstore-Dashboard-V1.pbix)
2. Open in Power BI Desktop
3. Model view → Ready for relationships!

