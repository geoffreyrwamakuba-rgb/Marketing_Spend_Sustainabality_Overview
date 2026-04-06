# Marketing Spend Overview - Protein Works

## Executive Summary
The dashboard provides a high-level overview of revenue, profitability, customer behaviour, and marketing efficiency, enabling stakeholders to quickly identify growth drivers and optimisation opportunities.

Tools Used: SQL, Python, Tableau

Data Sources: Data model based on Shopify, Google Analytics 4, Facebook Ads, Instagram & TikTok Analytics schemas. All data is synthetic.

## Dashboard
![alt text](https://github.com/geoffreyrwamakuba-rgb/Marketing_Spend_Sustainabality_Overview/blob/ed3b3fe62cf3d278b3d197a2bda40d5ac253bbc5/Marketing%20Dashboard.png)

## Business Problem
DTC ecommerce platforms face several key challenges:
- Understanding whether growth is driven by new customer acquisition or repeat purchasing
- Measuring the efficiency of marketing spend across channels
- Identifying which products and categories drive profitability
- Consolidating fragmented data across marketing and sales into a single source of truth
  
## Methodology
### Data Source
Python was used to generate realistic synthetic datasets
The data model is based on schemas from:
- Shopify (orders, products, customers)
- Google Analytics 4 (sessions, traffic sources)
- Facebook Ads, Instagram, and TikTok (campaign performance)
- The dataset includes 50k+ orders

The data is structured using a star schema:
- Fact tables: orders, line items, sessions, ad spend
- Dimension tables: customer, product, channel, campaign, date

Realism was introduced through Seasonality trends in demand and spend & Conversion rates tied to traffic sources

![alt text](https://github.com/geoffreyrwamakuba-rgb/Shopify_Overview__Protein_Works/blob/main/Ecommerce_Data_Model.svg)

### SQL Analysis
SQL was used to transform raw data into analytics-ready tables powering the dashboard.

Key transformations include:
- Combined revenue, new customers, and ad spend to calculate LTV, CAC, and LTV/CAC trends
- Marketing efficiency by traffic source
- Marketing KPI aggregation including total spend, budget utilisation, CVR, and ROAS
- Customer behaviour and lifecycle metrics (repeat rate, repurchase time, and YoY changes)
- Purchase frequency distribution

Advanced SQL techniques used:
- Nested CTEs (Common Table Expressions)
- Window functions - LAG() for YoY growth calculations (spend, ROAS, LTV)
- Defensive calculations
- Prevented division errors using NULLIF and COALESCE

## Key Insights & Recommendations

### Insight 1 – Google and YouTube are underperforming on conversion and ROAS

Google: low CVR (5.3%) and weak ROAS (3.4x) despite high spend

YouTube: lowest CVR (3.3%) and lowest ROAS (~2.0x)

👉 These channels drive traffic but fail to efficiently convert or monetise it.

### Recommendation:
- Reposition Google & YouTube as top-of-funnel channels
- Improve efficiency via better keyword targeting (Google)
- Retarget this traffic through high-performing channels (Instagram, TikTok, Email)

### Insight 2 – Marketing efficiency has significantly improved YoY, especially in 2025

LTV/CAC increases consistently across years:

2023: mostly ~3.5–5.3
2024: improves to ~5.0–6.2
2025: jumps to ~6.7–9.8

👉 This shows a step-change in efficiency, with 2025 delivering substantially higher return on acquisition spend.

### Recommendation:
- Scale marketing investment while maintaining efficiency thresholds
- Identify what changed in 2025: Channel mix or better targeting/creatives
- Double down on these drivers to sustain high LTV/CAC
