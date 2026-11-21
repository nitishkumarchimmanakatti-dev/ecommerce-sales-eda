# E-Commerce Sales & Customer Behavior Analysis using Python

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-blueviolet)

> **Portfolio EDA Project** | Mentorship Program: Artificial Intelligence (Batch: July 2026)

---

## 📌 Project Overview
An end-to-end Exploratory Data Analysis (EDA) investigating **541,909 international transactions** from a UK-based online retail business operating between December 2010 and December 2011. 

The primary business goal is to uncover **sales performance drivers**, **customer purchasing patterns**, **product demand dynamics**, **cancellation behavior**, and **high-value customer segments** to deliver data-backed recommendations for inventory optimization and marketing strategy.

---

## 📊 Dataset Information
* **Source:** [UCI Machine Learning Repository - Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)
* **Scale:** 541,909 rows × 8 attributes
* **Timeframe:** 01/12/2010 – 09/12/2011
* **Attributes:**
  * `InvoiceNo`: Unique 6-digit transaction identifier (prefixed with 'C' for cancellations).
  * `StockCode`: Unique 5-digit product code.
  * `Description`: Product name.
  * `Quantity`: Quantity of units purchased per transaction line.
  * `InvoiceDate`: Timestamp of transaction.
  * `UnitPrice`: Product price per unit in British Pounds (£).
  * `CustomerID`: 5-digit unique customer identifier.
  * `Country`: Country of customer residence.

---

## 🧹 Data Cleaning & Preprocessing Pipeline
1. **Duplicate Records:** Identified and purged **5,268 exact duplicate rows** (0.97% of total records).
2. **Cancellations & Returns:** Identified **3,836 cancelled invoices** (representing an overall **14.81% cancellation rate**). Filtered out negative quantities from net sales analysis.
3. **Data Quality Corrections:** Removed invalid bookkeeping and damaged inventory adjustments (`UnitPrice <= 0`).
4. **Guest Checkouts:** Handled **135,080 guest transactions (24.93%)** with unassigned `CustomerID`s, isolating them for general sales analysis while focusing customer segmentation on registered user accounts.
5. **Feature Engineering:**
   * `TotalSales` = `Quantity` × `UnitPrice`
   * Date/Time features: `Year`, `Month`, `YearMonth`, `DayOfWeek`, `Hour`.

---

## 🔍 Key Findings & Analytical Insights

### 1. Revenue & Order Economics
* **Average Order Value (AOV):** **£375.05** per invoice (Median: £145.40), showing strong right-skewness driven by commercial wholesale orders.
* **Geographical Dominance:** The **United Kingdom** accounts for **84.5%** of all revenue. Among international markets, the Netherlands, Germany, EIRE (Ireland), and France generate the highest export revenue.

### 2. Best-Selling Products
* **Top Revenue Generator:** `REGENCY CAKESTAND 3 TIER` generated over **£142,000+** in gross revenue.
* **Top Volume Item:** `WORLD WAR 2 GLIDERS ASSTD DESIGNS` sold over **54,000+ units**.

### 3. Customer Concentration (Pareto Principle / VIP Segment)
* High revenue concentration among top buyers: **VIP Customer ID 14646** alone spent **£280,206.02**, followed by **Customer ID 18102** (£259,657.30).
* The top 10 customers contribute a disproportionate share of global B2B revenue.

### 4. Seasonality & Shopping Timing
* **Peak Season:** A massive sales surge occurs in **Q4 (October – November)**, peaking at **£1.16M+ in November**, driven by pre-holiday corporate gifting and Black Friday stocking.
* **Peak Hours:** Transactions peak between **11:00 AM and 2:00 PM** (lunchtime rush).
* **Weekly Pattern:** Thursdays and Tuesdays see the highest order volumes. The warehouse operates Sunday–Friday (zero transactions on Saturdays).

### 5. Price Elasticity (Question 10)
* Scatter plot analysis and rank correlation confirmed a clear negative relationship between product price and purchase volume: high-priced items are predominantly ordered as single units, whereas lower-priced decorative novelties are purchased in dozens or hundreds.

---

## 📈 Visualizations Included in Analysis
This project implements the comprehensive 17-visualization suite:
- **3 Bar Charts:** Top 10 Products by Revenue, Top 10 Products by Quantity, Top 10 International Markets.
- **3 Histograms:** Order Value Distribution, Line Item Quantity Distribution, Unit Price Distribution.
- **3 Box Plots:** Order Value Outliers (Log Scale), Unit Price Range, Quantity Variation across Days of the Week.
- **2 Count Plots:** Transaction Frequency by Day of Week, Hourly Shopping Traffic.
- **2 Scatter Plots:** Unit Price vs. Quantity (Elasticity), Order Quantity vs. Total Revenue.
- **1 Correlation Heatmap:** Inter-variable Pearson & Spearman correlation matrix.
- **1 Time-Series Chart:** Monthly Sales & Order Volume Progression (Dec 2010 – Dec 2011).
- **2 Additional Specialized Plots:** Top 10 VIP Customer Revenue Share, Monthly Demand Trends for Top 5 Products.

---

## 💡 Strategic Business Recommendations
1. **VIP Loyalty & Account Management:** Assign dedicated B2B account managers to the top 20 wholesale buyers (led by Customer 14646) with tailored credit terms and volume rebates.
2. **Q4 Inventory Ramp-Up:** Initiate supply-chain reorders for high-demand seasonal SKUs by August to prevent stockouts during the October–November surge.
3. **Target International Expansion:** Focus digital advertising and localized shipping in high-performing European hubs: Netherlands, Germany, and France.
4. **Cart Abandonment / Guest Retargeting:** Incentivize the 25% guest checkouts with first-time registration discounts to capture customer email addresses for retention marketing.
5. **Mitigate 14.8% Cancellation Rate:** Audit top-cancelled SKUs for quality/description mismatches to reduce return logistics costs.

---

## 💼 Resume-Ready Project Summary
> *"Analyzed 540K+ international e-commerce transactions using Python, Pandas, Matplotlib, and Seaborn. Identified key revenue drivers, seasonal Q4 demand surges (£1.16M peak), a 14.8% cancellation rate, and customer purchase concentration, delivering data-backed recommendations for inventory stocking, B2B VIP retention, and European export expansion."*
