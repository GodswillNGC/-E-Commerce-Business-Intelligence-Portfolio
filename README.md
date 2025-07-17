# -E-Commerce-Business-Intelligence-Portfolio
An interactive Power BI dashboard for in-depth e-commerce analytics, featuring sales performance, customer behavior, category insights, and geographic distribution. Includes dynamic visuals, cross-filtering, DAX-driven KPIs, and multi-page navigation for a complete business intelligence experience.

# 📊 E-Commerce Business Intelligence Portfolio – Power BI Interactive Dashboard

![Power BI Dashboard Preview](./Visuals/Category_Performance.png)


## ✨ Project Overview

This project presents a **fully interactive and insight-rich Power BI dashboard** that analyzes a fictional e-commerce dataset. The dashboard is structured across four core business areas:

- 🔹 **Sales Performance Analysis**
- 🔹 **Customer Behavior Analytics**
- 🔹 **Category Performance**
- 🔹 **Geographic Analysis**

Through compelling visuals, smart filtering, and dynamic page navigation, the report transforms raw data into actionable business intelligence.

---

## 🧠 Business Objectives

- Evaluate overall sales health and revenue growth.
- Identify customer buying behavior and retention trends.
- Pinpoint top-performing and underperforming products.
- Understand how geography influences revenue and category sales.

---

## 📌 Key Features

### 📁 Multi-Page Navigation
The report is structured with **interactive buttons** that guide the user from one analysis page to another. Each page features a clean layout and is enhanced with dynamic visuals that update in response to user interactions with slicers and charts.

### 🧩 Interactivity
- Clicking a bar, pie slice, or country triggers **cross-filtering** across all related visuals.
- **Slicers** for category and continent refine the visual outputs, giving users complete control over the story they want to see.
- KPI cards update instantly based on user selections.

### 🧪 DAX-Driven Insights

The report uses **DAX formulas** to create powerful calculations, such as:



# 📈 Sales Performance Analysis

This section of the dashboard provides a high-level overview of the company's revenue performance, enabling stakeholders to assess the business's financial health at a glance.
![Power BI Dashboard Preview](./Visuals/Sales_Performance_Analysis.png)

## 📊 Key Visuals

KPI Cards: Total Revenue, Total Orders, Average Order Value (AOV)

Bar Chart: Revenue by Category

Line Chart: Quarterly Revenue Trend

Interactive Filters: Category selector, Date range

## 🧠 DAX Measures

Total Revenue = SUM(ecommerce_orders_2023[Quantity] * ecommerce_orders_2023[Unit Price])

Total Orders = COUNT(ecommerce_orders_2023[Order ID])

AOV = DIVIDE([Total Revenue], [Total Orders])

## 📌 Insights

Revenue remains relatively consistent across quarters with minor seasonal variations.

Home & Garden, Toys, and Clothing lead in category performance.

## 🧭 Navigation & Interactivity

Clicking any category filters all visuals across the page.

Navigation button links directly to Category or Customer Analysis sections.

# 👤 Customer Behavior Analytics

This report section dives into customer segmentation, gender demographics, and retention trends to understand the lifecycle and value of different customer groups.

📊 Key Visuals

Customer Retention Funnel: New vs Returning Customers

Donut Chart: Gender Distribution

Bar Chart: Top 5 Customers by Revenue

KPI Card: Total Unique Customers

🧠 DAX Measures

FirstPurchaseDate = CALCULATE(MIN(ecommerce_orders_2023[Order Date]), ALLEXCEPT(ecommerce_orders_2023, ecommerce_orders_2023[Customer ID]))

CustomerType = IF(ecommerce_orders_2023[Order Date] = ecommerce_orders_2023[FirstPurchaseDate], "New", "Returning")

Total Customers = DISTINCTCOUNT(ecommerce_orders_2023[Customer ID])

📌 Insights

Over 3,600 customers are new while 2,600 are returning, showing good retention.

Gender is nearly evenly split with a large number of unspecified entries.

🧭 Navigation & Interactivity

All visuals interact with each other on slicer or chart selection.

Buttons lead to Sales or Category Analysis pages.

📦 Category Performance

Here, we analyze how each product category contributes to revenue and sales volume, both globally and per country.

📊 Key Visuals

Treemap: Revenue by Product Category

Column Chart: Quantity Sold by Product

Table: Category Performance per Country

Top Cards: Top 3 Categories by Revenue

🧠 DAX Measures

Total Quantity = SUM(ecommerce_orders_2023[Quantity])

Revenue = ecommerce_orders_2023[Quantity] * ecommerce_orders_2023[Unit Price]

📌 Insights

Home & Garden, Toys, and Sports lead in both quantity sold and revenue.

Some regions prefer specific categories (e.g., Automotive in Germany, Beauty in Brazil).

🧭 Navigation & Interactivity

Slicer allows filtering by category to update the map and performance table.

Buttons guide users to Customer and Sales views.

🌍 Geographic Analysis

This page visually represents how revenue is distributed across continents and countries, helping identify geographical strengths.

📊 Key Visuals

Map: Revenue by Country

Stacked Bar Chart: Revenue by Continent

Table: Country-wise Revenue and Category Breakdown

🧠 DAX Measures

Total Revenue = SUM(ecommerce_orders_2023[Quantity] * ecommerce_orders_2023[Unit Price])

📌 Insights

North America and Europe dominate in total sales.

Australia and Brazil contribute significantly across various categories.

🧭 Navigation & Interactivity

Interactive continent and country filters update all visuals in real-time.

Navigation buttons return user to any previous dashboard section.

