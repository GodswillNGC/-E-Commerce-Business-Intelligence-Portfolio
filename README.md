# -E-Commerce-Business-Intelligence-Portfolio
An interactive Power BI dashboard for in-depth e-commerce analytics, featuring sales performance, customer behavior, category insights, and geographic distribution. Includes dynamic visuals, cross-filtering, DAX-driven KPIs, and multi-page navigation for a complete business intelligence experience.

# 📊 E-Commerce Business Intelligence Portfolio – Power BI Interactive Dashboard

![Power BI Dashboard Preview]("C:\Users\Ndubuisi Godswill\Pictures\Screenshots\Screenshot 2025-07-17 113228.png")

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

#### Customer Segmentation:
```DAX
FirstPurchaseDate =
CALCULATE(
    MIN(ecommerce_orders_2023[Order Date]),
    ALLEXCEPT(ecommerce_orders_2023, ecommerce_orders_2023[Customer ID])
)

CustomerType =
IF(
    ecommerce_orders_2023[Order Date] = ecommerce_orders_2023[FirstPurchaseDate],
    "New",
    "Returning"
)
Revenue Calculation:
DAX
Copy
Edit
Revenue = ecommerce_orders_2023[Quantity] * ecommerce_orders_2023[Unit Price]
Return Rate:
DAX
Copy
Edit
Return Quantity =
IF(ecommerce_orders_2023[Status] = "Returned", ecommerce_orders_2023[Quantity], 0)

Return Rate =
DIVIDE(SUM(ecommerce_orders_2023[Return Quantity]), SUM(ecommerce_orders_2023[Quantity]))
Funnel Stage Counts (using disconnected table):
DAX
Copy
Edit
CustomerFunnelCount =
SWITCH(
    SELECTEDVALUE(FunnelStages[FunnelStage]),
    "Total Customers", COUNTROWS(CustomerSummary),
    "New Customers", CALCULATE(COUNTROWS(CustomerSummary), CustomerSummary[CustomerType] = "New"),
    "Returning Customers", CALCULATE(COUNTROWS(CustomerSummary), CustomerSummary[CustomerType] = "Returning")
)
