# Nifty 500 Analytics Dashboard

**From Chaos to Clarity: Transforming 30 Years of Indian Stock Market Data into Actionable Insights**

---

## Executive Summary

- Built an end-to-end analytics pipeline for 500 Nifty stocks across 30 years (1996–2025)
- Automated data collection, cleaning, transformation, and modeling using Python and Power BI
- Converted raw prices into returns, volatility, and Sharpe Ratio for meaningful comparison
- Designed an interactive Power BI dashboard to analyze risk-adjusted performance instantly
- Demonstrated how mathematics and data science turn messy real-world data into clarity

---

## Project Overview

This project presents a comprehensive data analytics pipeline and interactive Power BI dashboard built on 30 years of historical data for all 500 stocks in India's Nifty 500 index (1996–2025).

What began as a mathematics poster competition entry evolved into a full-scale, real-world analytics solution that demonstrates how mathematics, statistics, Python, and data visualization come together to solve complex financial problems.

The dashboard enables users to:

- Compare any Nifty 500 stock
- Measure risk and returns
- Identify top and bottom performers
- Analyze long-term market behavior interactively

---

## Event Details

| Field        | Details                                                                 |
|--------------|-------------------------------------------------------------------------|
| Presented at | Dr. S. B. Nimse Amrit Mahotsav – Poster Exhibition                     |
| Date         | November 12, 2025                                                       |
| Venue        | Mathematics Department, New Arts, Commerce and Science College, Ahmednagar |
| Organized by | Mathematics Department (NACSC), Savitribai Phule Pune University, Indian Mathematical Society, Alumni Association |

---

## Project Team

| Member           | Role                                      |
|------------------|-------------------------------------------|
| Girish Sabale    | Project Lead, Dashboard Design & Visualization |
| Ganesh Gangarde  | Data Collection & Integration Pipeline    |
| Babita Mourya    | Data Transformation & Statistical Analysis |

---

## Problem Statement

Analyzing 500 stocks over 30 years presents several challenges:

- Massive data volume
- Missing values due to market holidays
- Inconsistent data formats
- Difficulty comparing stocks directly

Raw stock prices alone are misleading. Meaningful analysis requires percentage returns, volatility, and risk-adjusted metrics.

---

## Solution Summary

A six-phase analytics pipeline was built to address these challenges:

1. Automated data collection using Python
2. Consolidation of 500 individual stock files
3. Transformation from prices to percentage returns
4. Restructuring data for analytics (Unpivoting)
5. Mathematical modeling using DAX
6. Interactive Power BI dashboard design

---

## Project Workflow

### Phase 1: Data Collection

- **Source:** Yahoo Finance
- **Tool:** `yfinance` (Python)
- **Data:** Daily OHLC prices for 500 stocks (1996–2025)
- **Output:** 500 CSV files (~500+ MB)

---

### Phase 2: Data Consolidation

- Extracted Date and Close Price from each file
- Merged all stocks into a single dataset using Date as the key
- Result: One master CSV with 501 columns (Date + 500 stocks)

---

### Phase 3: Price to Returns Conversion

- Filled missing values using forward-fill
- Converted prices to daily percentage returns

**Formula:**

```
Daily Return = ((Price_today - Price_yesterday) / Price_yesterday) × 100
```

---

### Phase 4: Power BI Transformation

- **Problem:** 500 stocks stored as columns (wide format)
- **Solution:** Unpivot transformation in Power Query

**Result:** A normalized three-column dataset — Date, Stock Name, Daily Return

**Key Fix:**
- Converted Daily Return from text to decimal
- Replaced NaN and error values

---

### Phase 5: Analytics Engine (DAX Measures)

**1. Average Daily Return**
```dax
AVERAGE(Returns[Daily Return])
```

**2. Volatility (Risk)**
```dax
STDEV.P(Returns[Daily Return])
```

**3. Annualized Sharpe Ratio**
```dax
(Avg Daily Return / Volatility) * SQRT(252)
```

**4. Cumulative Trend Line**  
Robust calculation with error handling for long time series.

---

### Phase 6: Dashboard Design

#### Page 1: Welcome Screen
- Project overview
- Team details
- Navigation button

#### Page 2: Insights Dashboard

**Controls**
- Stock Selector (500 stocks)
- Date Range Slicer

**Key Metrics**
- Average Daily Return
- Volatility
- Sharpe Ratio

**Visualizations**
- Stock Performance Line Chart
- Risk–Return Treemap (all 500 stocks)
- Top 10 Sharpe Ratio Stocks
- Bottom 10 Sharpe Ratio Stocks
- Top 10 Most Volatile Stocks

---

## Mathematical and Statistical Foundations

**Statistics**
- Mean
- Standard Deviation
- Percentage Change

**Financial Mathematics**
- Daily Returns
- Risk vs Return
- Sharpe Ratio
- Annualization Factor (√252)

**Data Science Principles**
- Data normalization (wide to long format)
- Time-series analysis
- Error handling
- Pipeline optimization

---

## Challenges and Solutions

| Challenge               | Solution                                    |
|-------------------------|---------------------------------------------|
| Huge data volume        | Incremental merging and optimized pandas operations |
| Missing data            | Forward-fill interpolation                  |
| NaN imported as text    | Data type conversion and error replacement  |
| Dashboard lag           | Optimized DAX measures                      |
| Tight deadline          | Clear role division across team members     |

---

## Dataset Scale

| Attribute       | Detail                  |
|-----------------|-------------------------|
| Stocks          | 500 (Nifty 500)         |
| Time Period     | 1996–2025               |
| Records         | ~500,000+ data points   |
| Final PBIX Size | 500+ MB                 |

---

## Key Learnings

- Real-world data is messy and requires careful preprocessing
- Data structure matters more than tooling choices
- Simple solutions are often the most robust
- Collaboration accelerates problem-solving
- Mathematics powers modern analytics

---

## How to Reproduce This Project

1. Run the Python scripts to download historical stock data using `yfinance`
2. Merge individual stock CSV files into a master dataset
3. Convert price data into daily percentage returns
4. Load the final CSV into Power BI Desktop
5. Use **Power Query → Unpivot Columns** to normalize the dataset
6. Create DAX measures for return, volatility, and Sharpe Ratio
7. Refresh visuals and explore insights

---

## Future Enhancements

**Technical**
- Live market data integration
- Predictive analytics using machine learning
- Portfolio optimization
- Correlation and sector analysis

**Usability**
- Mobile responsiveness
- Exportable reports
- Saved views and alerts

**Scalability**
- Cloud databases (Azure SQL / Snowflake)
- Incremental data refresh
- Global market expansion

---

## Tools and Technologies

| Tool / Library        | Purpose                          |
|-----------------------|----------------------------------|
| Python 3.x            | Data collection and processing   |
| pandas                | Data manipulation                |
| yfinance              | Yahoo Finance data retrieval     |
| Power BI Desktop      | Dashboard design and publishing  |
| Power Query (M)       | Data transformation and unpivoting |
| DAX                   | Analytics measures and KPIs      |

---

## Contact

**Gangarde Ganesh**  
Project Lead – Data Visualization  
LinkedIn: [linkedin.com/in/ganesh-gangarde](https://www.linkedin.com/in/ganesh-gangarde-/)

---

## License

This project is intended for educational and research purposes. Please contact the project team before reusing or redistributing any part of this work.

---

> "From chaos to clarity — that is the power of mathematics, computation, and systematic thinking."
