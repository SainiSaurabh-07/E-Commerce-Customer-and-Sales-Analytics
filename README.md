# 🛒 E-COM Dashboard: E-Commerce Analytics & Insights

A dynamic, multi-page Power BI report built to explore e-commerce performance — covering customer behavior, sales trends, product analytics, delivery efficiency, and advanced market basket analysis.

---

## 1.Short Description / Purpose

The E-COM Dashboard is a comprehensive Power BI report designed to help e-commerce managers, product analysts, and business strategists monitor and analyze end-to-end marketplace performance. Built on 9 integrated datasets, the dashboard covers everything from customer churn and payment behavior to cross-category product affinity and revenue mix — enabling faster, data-driven decisions across sales, logistics, and marketing functions.

---

## 2.Tech Stack

The dashboard was built using the following tools and technologies:

- 🐍 **Python** – Used for data cleaning, transformation, and automated upload of all 9 datasets directly into Power BI via Python script integration.
- 📊 **Power BI Desktop** – Main data visualization platform for report creation, layout, and publishing.
- 📂 **Power Query** – Additional data shaping and preparation layer within Power BI.
- 🧠 **DAX (Data Analysis Expressions)** – Used for calculated measures, KPIs, churn logic, revenue mix percentages, and time-based comparisons.
- 📝 **Data Modeling** – Relationships established across all 9 tables to enable cross-filtering, aggregation, and market basket analysis.

---

## 3.Data Source

The dashboard is powered by **9 integrated datasets**, each cleaned in Python and uploaded into Power BI via a Python script:

| # | Dataset | Key Fields |
|---|---------|------------|
| 1 | **Orders** | order_id, order_status, purchase timestamp, delivery dates |
| 2 | **Sellers** | seller_id, seller location, local sales data |
| 3 | **Customers** | customer_id, location, activity status, churn flags |
| 4 | **Products** | product_id, category, photos, dimensions, weight |
| 5 | **Order Reviews** | review_score, review comment, delivery feedback |
| 6 | **Order Payments** | payment_type, payment_value, installments |
| 7 | **Order Items** | order_id, product_id, price, freight value, quantity |
| 8 | **Product Category** | category name (Portuguese & English translation) |
| 9 | **Geolocation** | zip code, latitude, longitude, city, state |

All datasets were cleaned and standardized in Python before being loaded into Power BI, ensuring data quality and consistency across all visuals.

---

## 4.Features / Highlights

### ⚙️ Data Pipeline

| Step | Tool | Description |
|------|------|-------------|
| 🧹 Data Cleaning | Python | All 9 datasets cleaned — nulls handled, types corrected, columns standardized |
| 🔗 Data Upload | Python Script | Processed datasets pushed directly into Power BI using Python script integration |
| 🔄 Data Modeling | Power BI | Relationships built across all 9 tables for unified cross-filtering |
| 📊 Report Generation | Power BI Desktop | Multi-page dashboards with KPIs, charts, tables, and advanced analytics |

---

### 5.Business Problem

E-commerce platforms generate massive volumes of transactional data across orders, payments, customers, and products — yet turning that data into actionable insight is a challenge. Key questions such as:

- How many customers are churning, and when did it peak?
- Which product categories are driving the most revenue?
- How does delivery performance impact customer satisfaction?
- Which product categories are frequently bought together?
- How are sales prices and order volumes shifting across categories?

…are difficult to answer quickly without a unified analytics layer across multiple data sources.

---

### 6.Goal of the Dashboard

To deliver a multi-page interactive analytics tool that:
- Tracks core e-commerce health metrics (customers, orders, sales, churn).
- Identifies top-performing product categories and payment trends.
- Measures logistics efficiency and its impact on customer reviews.
- Surfaces revenue contribution and cross-category buying patterns for strategic decisions.

---

### W7.alkthrough of Key Visuals

**Page 1 — Overview & Customer Analytics**

- **Key KPIs**
  - Total Customers: **75.65K**
  - Total Orders: **75.65K**
  - Total Sales: **10.80M**
  - Average Order Value: **$142.72**
  - Last 12 Months Inactive Customers: **41K**

- **Churned Customer Table**
  Year-wise customer churn breakdown: 252 churned in 2016, 34,534 in 2017, and 2018 status listed as "Cannot be determined" — highlighting a sharp churn surge that warrants retention strategy review.

- **Average Quantity by Product Photos** *(Area Chart)*
  Shows how the number of product photos correlates with average quantity ordered. A spike at 16 photos (avg 1.25) suggests richer product imagery drives slightly higher order quantities.

- **Order Count by Month, Year & Product Category** *(Small Multiples Line Chart)*
  Tracks order trends across 2016–2018 for each product category (agro industry, air conditioning, art, arts & craftmanship, etc.), enabling seasonal and category-level demand analysis.

- **Payment Value by Payment Type** *(Pie Chart)*
  - Credit Card: **10.34M (78.56%)** — dominant payment method
  - Boleto: **2.37M (17.97%)**
  - Voucher: **0.3M (2.25%)**
  - Debit Card: minimal share

---

**Page 2 — Product Performance & Logistics**

- **New Product Orders and Sales in Last 6 Months** *(Table)*
  Ranks product categories by new orders and sales value. Top categories:
  - health_beauty: 1,547 orders | $228,798
  - watches_gifts: 642 orders | $203,756
  - housewares: 1,343 orders | $180,044
  - Total: 14,806 orders | $2.41M in sales

- **Average Review Score by Delivery Status** *(Bar Chart)*
  On-time deliveries score **4.26** vs. late deliveries at **2.56** — a clear signal that delivery performance is a primary driver of customer satisfaction.

- **Logistics KPIs (Right Panel)**
  - Average Hours to Approve: **9.59 hrs**
  - Average Hours to Ship: **74.97 hrs**
  - Average Hours to Deliver: **262.12 hrs**

- **Change in Sales Price & Order Quantity by Category** *(Dual Line Chart)*
  Overlays price change % and order quantity change % across all product categories, helping identify where price elasticity is high or where volume is shifting independent of price.

---

**Page 3 — Advanced Analytics**

- **Local Sales Percentage by Seller ID** *(Table)*
  Breaks down each seller's share of local (same-state) sales, order count, and average review score. Overall local sales rate: **3.82%** across 262 orders — indicating most sales are cross-regional.

- **First 90-Day vs Last 90-Day Revenue % Change by Category** *(Table)*
  Compares early vs. recent revenue performance per category. Notable movers:
  - auto: **+111,960**
  - baby: **+51,980**
  - agro_industry_and_commerce: **+12,677**
  - Total net change: **+1,942,608**

- **Market Basket Analysis: Cross-Category Affinity** *(Matrix Table)*
  Advanced association rule analysis showing Support, Confidence, and Lift values between category pairs (e.g., auto × baby lift: 0.02; baby × bed_bath_table confidence: 0.01, lift: 0.38). Useful for cross-sell recommendations and bundling strategy.

- **Revenue Mix Analysis: Product Category Contribution** *(Color-coded Table)*
  Ranks all categories by % of total sales with traffic-light color coding (green → yellow → red):
  - watches_gifts: **9.18%**
  - health_beauty: **9.12%**
  - bed_bath_table: **7.92%**
  - sports_leisure: **7.32%**
  - Total: **100%**

---

### 8.Business Impact & Insights

- **Churn Prevention**: The sharp jump from 252 churned customers in 2016 to 34,534 in 2017 signals a critical retention problem — enabling targeted re-engagement campaigns.
- **Payment Strategy**: With 78.56% of sales via credit card, optimizing installment offers and credit card partnerships can directly impact conversion rates.
- **Delivery Improvement**: The 1.7-point review score gap between on-time and late deliveries (4.26 vs 2.56) shows logistics efficiency is directly tied to customer satisfaction and repeat purchase behavior.
- **Category Prioritization**: Revenue mix analysis helps merchandising teams double down on top contributors (watches, health & beauty) and investigate underperformers.
- **Cross-Sell Opportunities**: Market basket affinity data can power personalized recommendation engines and co-marketing campaigns between high-lift category pairs.
- **Seller Performance**: Local sales rate and review score by seller enables marketplace managers to identify and support high-potential regional sellers.

---

## 9.Screenshots

**Page 1 — Overview & Customer Analytics**
!(https://github.com/SainiSaurabh-07/E-Commerce-Customer-and-Sales-Analytics/blob/main/E-Commerce%20Customer%20and%20Sales%20Analysis.png)
