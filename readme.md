# McDonald’s Financial Performance & Valuation (Python + BI)

A production‑style financial analysis project that transforms 21 years of McDonald’s data (2002–2022, plus 2023 actuals) into investor‑ready insights, combining Python modeling with BI dashboards for profitability, leverage, valuation, and dividend analysis.​

## 📌 Table of contents

- [Overview](#overview)
- [Business problem](#business-problem)
- [Dataset](#dataset)
- [Tech stack](#tech-stack)
- [Project structure](#project-structure)
- [Data preparation](#data-preparation)
- [Feature engineering](#feature-engineering)
- [Analysis & modeling](#analysis--modeling)
- [Dashboards delivered](#)
- [Key metrics](#key-metrics)
- [How to run project](#how-to-run-project)
- [Findings snapshot](#findings-snapshot)
- [Limitations](#limitations)
- [Author & contact](#author--contact)

## Overview
This repository turns McDonald’s long‑term financial history into a reusable analytical asset by standardizing company‑level metrics, building forecasting and DCF models in Python, and surfacing decision‑ready views of profitability, capital structure, shareholder returns, and valuation multiples. The project follows common buy‑side and equity‑research workflows.​​

## Business problem

- **Performance**: Investors and analysts need a clear view of how McDonald’s has created value over two decades—whether through revenue growth, margin expansion, or financial engineering.​
- **Risk**: Management and lenders care about how leverage, cash generation, and dividend commitments affect downside risk across cycles.​
- **Valuation**: Equity analysts require a consistent framework to judge whether the current share price is justified relative to historic fundamentals and forward cash flows.​

## Dataset
- **Source**: Curated CSV of McDonald’s annual metrics (2002–2022) plus 2023 actuals from the company’s financials.​​
- **Core fields (in USD billions unless noted)**:
- Market cap, Revenue, Earnings, P/E, P/S, P/B
- Operating Margin (%), EPS, Shares Outstanding (B)
- Cash on Hand, Dividend Yield (%), Dividend per share
- Net assets, Total assets, Total debt, Total liabilities

This structure is ideal for long‑horizon ratio analysis, trend study, and simplified valuation without line‑item statements.​

## Tech stack
Python (Pandas, NumPy, scikit‑learn, Matplotlib/Seaborn) for data cleaning, feature engineering, CAGR and ratio calculations, regression‑based forecasting, and DCF modeling.​
Power BI (or Tableau) for interactive dashboards: KPI cards, time‑series charts, and scenario visuals.​
Git / GitHub for version control, documentation, and reproducibility.​

## Project structure
````
├─ Data/
│  ├─ McDonalds_Financial_Statements.csv         # Raw 2002–2022 data
│  └─ McDonalds_Dashboard_Ready.csv              # Engineered metrics for BI
├─ Notebooks/
│  └─ mcdonalds_financial_analysis.ipynb         # Main analysis & modeling
├─ Visuals/
│  ├─ 01_revenue_earnings.png
│  ├─ 02_operating_margin.png
│  ├─ 03_valuation_multiples.png
│  ├─ 04_leverage_trend.png
│  ├─ 05_dividend_trend.png
│  └─ 06_roa_roe.png
├─ Power Bi/
│  └─ McDonalds_Financials_Dashboard.pbix        # Power BI dashboard (optional)
├─ Docs/
│  ├─ kpi_definitions.md
│  └─ executive_summary.pdf
└─ README.md
````

## Data preparation

- **Validation**: Checked shape, data types, and missing values; dataset has 21 years × 17 columns with no nulls.​
- **Sorting**: Ordered observations by Year for correct time‑series analysis.​
- **Units**: Confirmed all monetary fields are in billions and percentages are stored as 0–100 values; kept billions for analysis and labeled axes accordingly.​

## Feature engineering

Key engineered metrics created in Python:​​
- **Growth**: Revenue, Earnings, Market Cap, and EPS YoY growth and 20‑year CAGR.
- **Profitability**: Net Margin %, ROA %, ROE %, Operating Margin in decimal form.
- **Capital structure**: Debt‑to‑Equity, Debt‑to‑Assets %, Net Debt, Cash‑to‑Assets %.
- **Shareholder returns**: Dividend Payout Ratio, Dividend growth, Dividend Yield (decimal).
- **Valuation diagnostics**: Implied Revenue‐to‑Earnings growth proxies from P/S vs P/E.

All metrics are exported to McDonalds_Dashboard_Ready.csv for direct BI consumption.

## Analysis & modeling

- **Trend analysis**: Compared pre‑crisis, crisis (2008–09), recovery (2010–19), and COVID/recovery (2020–22) periods on revenue and operating margin.​
- **Forecasting**: Used linear regression on Year vs Revenue and Earnings to project 2023–2027 base‑case values, plus conservative and bull scenarios.​​
- **Valuation**: Built a simplified DCF with 5‑year FCF proxy from earnings, 8% WACC, and 2% terminal growth to estimate enterprise value, equity value, and implied price vs 2022 market cap.​​

## Dashboards delivered

- **Performance Overview**: Revenue, Earnings, Operating Margin, and Net Margin trends with recession markers and CAGR annotations.
- **Capital Structure & Risk**: Debt‑to‑Assets, Net Debt, Cash position, and ROA/ROE in a single view for leverage monitoring.
- **Valuation & Shareholder Returns**: P/E, P/S, P/B over time, dividend per share and yield trends, and DCF/price comparison tiles.

## Key metrics
- **Revenue CAGR (2002–2022)**: 2.1%; Earnings CAGR: 8.1%.​
- **Operating Margin**: 10.8% → 33.8% over the sample, reflecting franchising and efficiency gains.​​
- **Debt‑to‑Assets**: 41.6% → 95.2%, with Net Debt rising from $9.6B to $45.5B, indicating a leveraged, shareholder‑return‑focused strategy.​​
- **2022 P/E**: 31.3× vs 21.7× long‑run average; DCF fair value ≈ $121.7B vs $193.0B market cap under conservative assumptions.​​

## How to run project

Clone repository

git clone <repo-url>

Place McDonalds_Financial_Statements.csv in /data if not already present.

Run notebook

Open notebooks/mcdonalds_financial_analysis.ipynb.

Execute cells in order: loading → preparation → feature engineering → analysis → forecasting → DCF → exports.​

Generate visuals

Running the plotting cells will save PNGs into /visuals for use in reports and your portfolio.​

Build Power BI dashboard (optional)

Import data/McDonalds_Dashboard_Ready.csv into Power BI.

Recreate KPI cards and charts following docs/kpi_definitions.md.

## Findings snapshot

McDonald’s shifted from volume‑driven growth to high‑margin, capital‑light franchising: revenue grew slowly, but earnings and margins improved significantly.​​
The company proved resilient in 2008–09 and 2020, maintaining strong margins despite macro shocks, confirming its defensive profile.​​
Leverage increased materially; high Debt‑to‑Assets and Net Debt support aggressive dividends and buybacks but raise sensitivity to interest rates and downturns.​​
Under conservative DCF assumptions, the stock appears fully valued to expensive, with limited upside for growth investors but solid support for income‑oriented holders.​​

## Limitations

Dataset is company‑level and annual; no segment or geographic breakdowns, so line‑of‑business margin analysis is out of scope.

## Author & Contact

**Ganesh_Rao**  
*Data Analyst & Business Intelligence*

🎯 **Specialized in**: healthcare Analytics, Customer Analytics, Financial Analysis, Statistical Modeling  
📊 **Experience**: Advanced EDA, Python Programming, Business Intelligence  
🎓 **Focus Areas**: Data Analytics, SQL, Machine Learning, Statistical Analysis, Power Bi

### Connect with me:
📧 **Email**: [jganeshrao5@gmail.com](mailto:jganeshrao5@gmail.com)  
🔗 **LinkedIn**: [linkedin.com/in/j-ganesh-rao-055ba2279](https://linkedin.com/in/j-ganesh-rao-055ba2279)  
🐙 **GitHub**: [https://github.com/GaneshRaogit](https://github.com/GaneshRaogit)  

---
*This project demonstrates advanced analytical skills, attention to data quality, and ability to derive actionable business insights from complex datasets. The comprehensive approach showcases proficiency in data science methodologies and business acumen essential for data analyst roles.*
