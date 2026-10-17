# FUTURE_DS_03


# 📊 November E-commerce Sales & Customer Behavior Dashboard

## 📌 Project Overview

This project presents an interactive **Power BI dashboard** designed to analyze November e-commerce event data. The dashboard helps understand sales performance, product and brand performance, customer activity, and shopping behavior through interactive visualizations and DAX measures.

The report transforms raw event-level data into meaningful business insights that can support data-driven decision-making.

## 🎯 Project Objectives

- Analyze overall sales performance during November.
- Identify top-performing products, brands, and categories.
- Track purchase events and customer activity.
- Understand user sessions and event distribution.
- Analyze hourly shopping activity.
- Explore the customer purchase funnel, where event data supports it.
- Present key performance indicators (KPIs) through an interactive dashboard.

## 🗂️ Dataset Information

The dataset contains the following columns:
Link:https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store
| Column Name | Description |
|---|---|
| Event Date | Date on which the event occurred |
| Event Time | Time at which the event occurred |
| Event Type | Type of user activity, such as view, cart, or purchase |
| Product ID | Unique identifier of a product |
| Category ID | Identifier of the product category |
| Category Code | Product category code or label |
| Brand | Product brand |
| Price | Recorded product price |
| User ID | Identifier of the user |
| User Session | Identifier of the user session |

> **Note:** Revenue calculations depend on the meaning of the `Price` column and the structure of purchase events. Purchase-event counts should not automatically be treated as distinct orders.

## 🛠️ Tools & Technologies

- **Power BI Desktop** – Dashboard development and visualization
- **Power Query** – Data cleaning and transformation
- **DAX (Data Analysis Expressions)** – Measures and calculations
- **Data Visualization** – KPI cards, line charts, bar charts, column charts, and donut charts
- **GitHub** – Project documentation and version control

## 📈 Dashboard Pages

![November Sales Overview](https://github.com/Malayasis-Banerjee/FUTURE_DS_03/blob/main/Screenshot%202026-10-17%20115924.png)
### 1. Sales Overview

Provides a high-level view of November performance.

**Key metrics and visuals:**
- Total Revenue
- Total Purchases
- Unique Customers
- Unique Sessions
- Daily Revenue Trend
- Revenue by Category
- Revenue by Brand
- Event Type Distribution

### 2. Product & Brand Analysis

Focuses on product performance and category-level comparisons.

**Key visuals:**
- Top 10 Products by Revenue
- Revenue by Brand
- Purchases by Category
- Average Product Price by Brand
- Product Performance Table

### 3. Customer & Event Analysis

Explores customer activity and shopping behavior.

**Key metrics and visuals:**
- Total Events
- Unique Customers
- Unique Sessions
- Events by Type
- Hourly Activity Analysis
- User Activity by Brand
- Purchase Funnel, if supported by the available event types

## 📐 Key DAX Measures

### Total Events

```dax
Total Events =
COUNTROWS(SalesData)
```

### Unique Customers

```dax
Unique Customers =
DISTINCTCOUNT(SalesData[User ID])
```

### Unique Sessions

```dax
Unique Sessions =
DISTINCTCOUNT(SalesData[User Session])
```

### Total Purchases

```dax
Total Purchases =
CALCULATE(
    COUNTROWS(SalesData),
    SalesData[Event Type] = "purchase"
)
```

### Total Revenue

```dax
Total Revenue =
CALCULATE(
    SUM(SalesData[Price]),
    SalesData[Event Type] = "purchase"
)
```

**Important:** The revenue measure assumes purchase-event rows contain the appropriate transaction prices. Validate the data before using this measure for financial reporting.

## 🧹 Data Preparation

The data preparation process includes:

1. Importing the November dataset into Power BI.
2. Assigning appropriate data types to each column.
3. Checking missing and duplicate records.
4. Validating product prices and event types.
5. Checking date and time values.
6. Reviewing category and brand inconsistencies.
7. Creating DAX measures for dashboard KPIs.
8. Validating calculations against the source data.

## 🎛️ Interactive Features

- Date filtering
- Brand filtering
- Category filtering
- Event type filtering
- Cross-filtering between visuals
- Drill-down and data exploration, where configured
- Interactive KPI cards and charts

## 💡 Business Insights

The dashboard can help answer questions such as:

- Which products generate the highest recorded revenue?
- Which brands perform best in terms of purchase value?
- Which categories receive the most purchases?
- How many unique customers and sessions are recorded?
- At what times do users show the highest activity?
- How are user events distributed across views, cart activity, and purchases?
- Where might the customer purchase funnel need improvement?

Actual findings should be added after analyzing the dataset and dashboard results.

## 📁 Project Structure

```text
November-Ecommerce-PowerBI-Dashboard/
│
├── README.md
├── data/
│   └── november_sales.csv
├── dashboard/
│   └── november_sales_dashboard.pbix
└── screenshots/
    ├── sales_overview.png
    ├── product_brand_analysis.png
    └── customer_event_analysis.png
```

*The structure above is a suggested organization. Add only files that are actually included in your repository.*

## 🚀 How to Use

1. Clone or download this repository.
2. Open the `.pbix` file using Power BI Desktop.
3. If required, update the data source path.
4. Refresh the dataset.
5. Navigate between the report pages.
6. Use slicers to explore the data by date, brand, category, and event type.

## 📊 Expected Outcomes

- Better visibility into product and brand performance.
- Clearer understanding of customer activity and shopping sessions.
- Identification of high-activity periods.
- Improved understanding of event-level e-commerce behavior.
- A foundation for data-driven business recommendations.

## 🔮 Future Improvements

- Add a proper order identifier for accurate order-level KPIs.
- Develop a validated customer conversion funnel.
- Add month-over-month comparisons when more months become available.
- Introduce customer retention and repeat-purchase analysis.
- Add automated refresh and scheduled reporting.
- Improve product-level analysis using product names and additional attributes.

## 👨‍💻 Author

**Malayasis Banerjee**

MCA Student | Aspiring Data Analyst

Areas of Interest: Data Analytics, Power BI, SQL, Python, and Business Intelligence.

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

*Built with Power BI to turn e-commerce event data into actionable insights.*
