# Project Overview:
- A Retail store business with a variety of products wants to analyze its sales performance, customer purchasing behavior, and product trends to make data-driven business decisions.

---

## Objective:
- The objective of this project was to clean, transform, model data and analyze store's sales data and build an interactive PowerBI dashboard to track key sales metrics and customer trends.

---

## Dataset:
The project utilized a relational database consisting of:
- Fact Sales Table: Transactional records containing units sold, order dates, and high volumes of null values in revenue columns.
- Dim Product Table: Master list of product IDs and unit prices.
- Dim Promotion Table: Detailed promotion types, including text-based discount descriptions.
- Dim Customers table: Deatails of the customers.


---

## Data Engineering & Transformation (Power Query):
Performed ETL to restore data integrity and prepare the model:

* **Data Imputation via Merging:** Performed **Left Outer Joins** to bring `Price` and `Discount %` into the Fact table, filling 100% of the null values.
* **Custom Business Logic:** Engineered **M-code formulas** to calculate `Total Sales` (Units * Price) and `Discount Value` (Sales * %).
* **Schema Cleanup:** Standardized data types (e.g., changing ID columns to **Text** to optimize the model) and utilized **Column Profiling** to ensure 100% data quality.
* **Order Tracking:** Added an **Index Column** to create a unique identifier for every transaction, enabling accurate "Total Order" card visuals.

## Data Modeling
* **Star Schema Implementation:** Organized tables into a **Star Model** to reduce join complexity and improve report refresh speeds.
* **Dual-Date Table Logic:** Created two independent date tables using `CALENDARAUTO()`.
* **Relationship Engineering:** Established one **Active** and one **Inactive relationship** between the date tables and the Fact table to facilitate complex **Period-over-Period** comparisons.

---

## Business Insights:
- Apple Iphone 14 is the top selling product while colgate toothpaste is at the bottom.
- Net sales kept declining right from 2020 to 2022 from where it increased till 2023 to again decrease sharply from 2023 to 2024.
- Discount value was highest during summer sale and lowest during Diwali
- Analysis of the Sales by City chart reveals that Delhi is the primary revenue driver, significantly outperforming other urban centers.
- 'Clothing' and 'Electronics' categories consistently generate the highest transaction volumes;
   however, a deep dive into profit margins shows that high-volume items are not always the most profitable.
- A select group of "Power Users" who contribute to a disproportionate share of total revenue.
- Identified that specific sub-categories (like Accessories) have lower overhead costs, providing a better "Profit-per-Unit" ratio despite lower total sales.

---

## Suggestions:
- Suggest performing a "Frequently Bought Together" analysis. For example, if people in Delhi buy Electronics, do they also buy specific Accessories? This helps in cross-selling.
- Recommend adding a Trend Line or a Forecasting Model in the next version of the dashboard to predict sales for the next 3 months based on historical data.
- Since Delhi is the leader, suggest a "Local Hero" promotion to maintain dominance, while testing "Expansion Discounts" in lower-performing cities like Kanpur to increase market share.
- While Delhi leads, cities like Lucknow and Kanpur show steady baseline sales but lack the "peak" volume seen in the capital,
  suggesting an opportunity for targeted regional marketing campaigns.

