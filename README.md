# Retail Sales & Profitability Performance Storyboard

## Project Objective
The goal of this project is to construct a multi-page interactive Power BI storyboard that transforms raw transaction data into tactical business insights. By following a top-down data narrative structure (Executive Summary → Geographic Deep-Dive → Product Root Cause), this dashboard isolates systemic profit losses and evaluates the impact of promotional discounting on the company's bottom line.

---

## Key Business Insights Uncovered

1. **The Headline (Page 1):** The business maintains a healthy continuous revenue line ($2.30M in total sales) but operates on a constrained overall **Profit Margin of 12.47%**, identifying clear inefficiencies in cost retention.
2. **The Geographic Friction (Page 2):** Regional analysis reveals that while the East and West regions are highly lucrative, major states like Texas and Ohio are heavily bleeding profits despite generating high sales volumes.
3. **The Root Cause (Page 3):** Portfolio matrix mapping isolates **Tables** and **Bookcases** as severe loss-making segments. By crossing this data with promotional tracking, the pipeline proves the losses are directly driven by aggressive over-discounting rather than a lack of market demand.

---

## Technical Architecture & Toolset
* **BI Platform:** Power BI Desktop
* **Calculations Language:** DAX (Data Analysis Expressions)
* **Design Philosophy:** Minimalist corporate layout, conditional diverging color scales for alert routing, and a strict 0% data-ink redundancy policy.

### Custom DAX Measures Implemented:
```dax
// 1. Gross Revenue Accumulation
Total Sales = SUM('Sample - Superstore'[Sales])

// 2. Net Earnings Accumulation
Total Profit = SUM('Sample - Superstore'[Profit])

// 3. Operational Efficiency Ratio (with safe zero-division handling)
Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)
