# Global Superstore Sales Analysis: Identifying Revenue Leakage and Market Inefficiency
Revenue is vanity, profit is sanity. This project uncovers how a global retailer managed to generate $12.6M in sales while over half of its transactions were actually losing money. Uncovered that 52% of orders were unprofitable due to undisciplined discounting and identified $136K+ in losses across Africa/EMEA markets.

## Project Summary
A comprehensive sales performance analysis of a global superstore
covering 51,290 orders across 7 markets, 3 product categories, and
4 years (2011–2014). The goal was to identify what drives revenue
and profitability — and where the business is losing money despite
strong sales growth.

## Dataset Overview
| Table | Rows | Description |
|---|---|---|
| Orders | 51,290 | Primary fact table — all transactional data |
| Returns | 1,174 | Returned order records |
| People | 15 | Regional manager assignments |

**Period:** January 2011 — December 2014
**Coverage:** Global — all major markets and continents

## Key Columns in the Dataset
| Column | Description |
|---|---|
| order_id | Unique order identifier |
| order_date / ship_date | Order and shipment dates |
| customer_name / segment | Customer details |
| category / sub_category | Product classification |
| sales / profit / discount | Core financial metrics |
| market / region / country | Geographic hierarchy |
| ship_mode / shipping_cost | Logistics data |

## Tools Used
| Tool | Purpose |
|---|---|
| Microsoft Excel | Data profiling, cleaning, calculated columns, PivotTable analysis |
| Microsoft Power BI | Data modelling, DAX measures, interactive dashboard |
| Power Query | Table relationships and data transformation |
| DAX | Custom KPI measures and time intelligence |

## Data Cleaning & Preparation
- Confirmed 51,290 rows and 21 columns with no missing values
- Verified and corrected date and numeric column formats
- Identified 3-table relational structure for Power BI modelling
- Engineered 5 calculated columns in Excel:
  - `profit_margin_pct` — Profit ÷ Sales × 100
  - `delivery_days` — Ship Date minus Order Date
  - `revenue_band` — High / Medium / Low by sales value
  - `profit_status` — Profit or Loss flag
  - `discount_band` — No / Low / Medium / High discount

## Key Questions & Analysis
1. Which products and sub-categories are profitable vs loss-making?
2. Which global markets generate losses despite high sales?
3. How does discounting affect profit margins across categories?
4. Is the business growing sustainably year on year?
5. What seasonal patterns exist and how predictable are they?

## Key Insights
- **52% of orders are unprofitable** — 13K of 25K total orders lose money
- **Tables sub-category: -24.2% margin** — $757K sales, -$64K profit
- **Africa and EMEA both loss-making** — -14.4% and -14.1% margins
- **High Discount = guaranteed losses** — negative margins across all categories
- **51.5% revenue growth** — sales from $2.26M to $4.30M over 4 years
- **Profit not keeping pace with sales** — unsustainable growth trajectory
- **Q4 dominates every year** — Nov-Dec peak consistent all 4 years

## Recommendations
1. Cap discounts at 10% maximum — implement governance and manager approval
2. Restructure Africa and EMEA — raise prices, cut shipping costs, focus on margins
3. Build a seasonal commercial calendar — plan around the predictable Q4 peak

## Dashboard / Visualization
The Power BI dashboard contains 4 report pages:

| Page | Focus |
|---|---|
| Executive Summary | KPIs, sales trend, category and market overview |
| Product Analysis | Sub-category profit, discount impact matrix, scatter |
| Global Performance | World map, market and regional profitability |
| Trends Over Time | Monthly trends, YoY growth, seasonal patterns |

## Project Structure
├── data/
│   └── global_superstore.xlsx
├── dashboard/
│   └── superstore_dashboard.pbix
├── report/
│   └── Superstore_Sales_Analysis.pptx
├── screenshots/
│   ├── executive_summary.png
│   ├── product_analysis.png
│   ├── global_performance.png
│   └── trends_over_time.png
└── README.md

## Afodunrinbi Samad Akinkunmi
Data Analyst | Excel | Power BI
[LinkedIn] | [Medium Article]
