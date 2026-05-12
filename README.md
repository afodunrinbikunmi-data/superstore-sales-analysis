## Global Superstore Sales Analysis: Identifying Revenue Leakage and Market Inefficiency
Revenue is vanity, profit is sanity. This project uncovers how a global retailer managed to generate $12.6M in sales while over half of its transactions were actually losing money. Uncovered that 52% of orders were unprofitable due to undisciplined discounting and identified $136K+ in losses across Africa/EMEA markets.

## Project Summary
A comprehensive sales performance analysis of a global superstore covering 51,290 orders across 7 markets, 3 product categories, and
4 years (2011–2014). The goal was to identify what drives revenue and profitability and where the business is losing money despite strong sales growth.

## Dataset Overview
| Table | Rows | Description |
|---|---|---|
| **Orders** | 51,290 | Primary fact table — all transactional data |
| **Returns** | 1,174 | Returned order records |
| **People** | 15 | Regional manager assignments |

**Period:** January 2011 — December 2014  
**Coverage:** Global — all major markets and continents

## Key Columns in the Dataset
| Column | Description |
|---|---|
| **order_id** | Unique order identifier |
| **order_date / ship_date** | Order and shipment dates |
| **customer_name / segment** | Customer details |
| **category / sub_category** | Product classification |
| **sales / profit / discount** | Core financial metrics |
| **market / region / country** | Geographic hierarchy |
| **ship_mode / shipping_cost** | Logistics data |

## Tools Used
| Tool | Purpose |
|---|---|
| **Microsoft Excel** | Data profiling, cleaning, calculated columns, PivotTable analysis |
| **Microsoft Power BI** | Data modelling, DAX measures, interactive dashboard |
| **Power Query** | Table relationships and data transformation |
| **DAX** | Custom KPI measures and time intelligence |

## Data Cleaning & Preparation
- Confirmed 51,290 rows and 21 columns with no missing values
- Verified and corrected date and numeric column formats
- Identified 3-table relational structure for Power BI modelling
- Engineered 5 calculated columns in Excel:
  - **`profit_margin_pct`** — Profit ÷ Sales × 100
  - **`delivery_days`** — Ship Date minus Order Date
  - **`revenue_band`** — High / Medium / Low by sales value
  - **`profit_status`** — Profit or Loss flag
  - **`discount_band`** — No / Low / Medium / High discount

## Data Engineering (Power Query)
The raw data was transformed to ensure analytical readiness. Key steps included:
- **Feature Engineering**: Created the Discount Band using conditional logic to segment orders into No (0%), Low (0.1-20%), Medium (21-50%), and High (>50%) categories.
- **Date Normalization**: Extracted Year, Month, and Quarter from the Order Date for time-series consistency.
- **Relationship Cleanup**: Standardized Region names across the Orders and People tables to ensure a clean Many relationship

## Data Modeling
A Star Schema was implemented in Power BI:
- **Fact Table**: Orders (Transactional data).
- **Dimension Tables**: Returns (linked via Order ID) and People (linked via Region).
- **Relationship Logic**: All relationships are Many with cross-filter direction set to "Single" to maintain model performance and data integrity.
![Image Description](https://github.com/afodunrinbikunmi-data/superstore-sales-analysis/blob/main/star%20schema%20superstore.PNG)

The following measures were engineered to drive the dashboard's KPIs:
 - **`Total Sales`**
 - **`Total Profit`**
 - **`Profit Margin`**
 - **`YoY Growth`**
 - **`Unprofitable Orders`**
 - **`Unprofitable Rate %`**
 - **`YoY Sales Growth`**
 - **`Return Rate %`**
 - **`Avg Delivery Days`**
 - **`Profit per Order`**
![Image Description](https://github.com/afodunrinbikunmi-data/superstore-sales-analysis/blob/main/new%20measure%20table%20superstore.PNG)

## Key Questions & Analysis
- Which products and sub-categories are profitable vs loss-making?
- Which global markets generate losses despite high sales?
- How does discounting affect profit margins across categories?
- Is the business growing sustainably year on year?
- What seasonal patterns exist and how predictable are they?
![Image Description](https://github.com/afodunrinbikunmi-data/superstore-sales-analysis/blob/main/superstore_pivot%20table.png)

## Key Insights
- **52% of orders are unprofitable** — 13K of 25K total orders lose money
- **Tables sub-category: -24.2% margin** — $757K sales, -$64K profit
- **Africa and EMEA both loss-making** — -14.4% and -14.1% margins
- **High Discount = guaranteed losses** — negative margins across all categories
- **51.5% revenue growth** — sales from $2.26M to $4.30M over 4 years
- **Profit not keeping pace with sales** — unsustainable growth trajectory
- **Q4 dominates every year** — Nov-Dec peak consistent all 4 years

## Recommendations
- Cap discounts at 10% maximum — implement governance and manager approval
- Restructure Africa and EMEA — raise prices, cut shipping costs, focus on margins
- Build a seasonal commercial calendar — plan around the predictable Q4 peak


## Dashboard/Visualization

- **Executive Summary**: KPIs, sales trend, category and market overview
![Image Description](https://github.com/afodunrinbikunmi-data/superstore-sales-analysis/blob/main/executive%20summary%20dashboard%201.png)
- **Product Analysis**: Sub-category profit, discount impact matrix, scatter
![Image Description](https://github.com/afodunrinbikunmi-data/superstore-sales-analysis/blob/main/product%20analysis%20dashboard%20new%201.png)
- **Global Performance**: World map, market and regional profitability
![Image Description](https://github.com/afodunrinbikunmi-data/superstore-sales-analysis/blob/main/global%20performance%20dashboard%201.png)
- **Trends Over Time**: Monthly trends, YoY growth, seasonal patterns
![Image Description](https://github.com/afodunrinbikunmi-data/superstore-sales-analysis/blob/main/trends%20over%20time%20dashboard%201.png)

## Limitations
While this analysis provides deep insights into the profitability crisis, several data constraints should be noted:
* **Financial Granularity:** The dataset lacks a breakdown of **COGS (Cost of Goods Sold)** and specific overheads, meaning profit is analyzed at a transactional level without visibility into manufacturing or storage costs.
* **Macroeconomic Factors:** As a global dataset, the results do not account for **currency fluctuations** or inflation rates in markets like Africa and EMEA between 2011 and 2014, which may have impacted localized profitability.
* **Fixed Logistics:** Shipping costs are recorded as static values per order, which does not reflect real-world variables like fuel surcharges or bulk-freight negotiated rates.
* **Customer Context:** Missing demographic data (age, income, industry) limits the ability to perform a full **Customer Lifetime Value (CLV)** analysis beyond basic purchase history.

## Conclusion
- **The Profitability Gap**: Identified that while revenue is scaling rapidly, profit is leaking through loss-making product categories and underperforming regional markets.

- **Operational Diagnosis**: Uncovered a "reactive" seasonal cycle; the business currently responds to demand shifts rather than using predictive planning to protect margins.

- **Data-Driven Visibility**: Transformed raw data into a diagnostic tool that makes hidden losses visible and actionable for stakeholders.

[Read The Full Article Medium](https://medium.com/@afodunrinbikunmi/global-superstore-sales-analysis-identifying-revenue-leakage-and-market-inefficiency-e7b9bdc4e41d)

### Project Structure

```text
├── data/
│   └── global_superstore.xlsx
├── dashboard/
│   └── superstore_dashboard.pbix
├── report/
│   └── Superstore_Sales_Analysis.pptx
├── png/
│   ├── executive_summary.png
│   ├── product_analysis.png
│   ├── global_performance.png
│   └── trends_over_time.png
└── README.md
```

## About me
Afodunrinbi Samad Akinkunmi
I am a Certified Data Analyst with a strong passion for transforming raw data into meaningful insights that support informed decision-making. My work focuses on exploring datasets, identifying patterns, and communicating findings in a clear and impactful way. I enjoy approaching problems analytically, breaking them down into structured steps, and uncovering the story behind the data. Beyond data analysis, I am actively expanding towards becoming a Data Scientist, with an interest in building predictive modeling and advanced analytics.

Data Analyst | Excel | Power BI | Python | SQL | Figma

Connect With Me On - [LinkedIn](https://www.linkedin.com/in/akinkunmiafod) | [Medium](https://medium.com/@afodunrinbikunmi) | Gmail: afodunrinbikunmi@gmail.com
