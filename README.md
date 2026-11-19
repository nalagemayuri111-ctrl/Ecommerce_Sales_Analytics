# E-Commerce Sales Analysis

SQL analysis of an e-commerce database with three tables, using MySQL to answer business questions about revenue, profit and product performance.

## Project Overview

I built a MySQL database with three related tables (customers, products and order items), loaded about 400,000 order lines, and wrote SQL queries to answer 30 business questions. The queries use aggregate functions, GROUP BY, HAVING, joins and subqueries.

## Dataset

- **Source:** [add the dataset name and link]
- **Tables:**
  - `customer_master`: 25,000 customers (segment, city, region and more)
  - `product_catalog`: 1,175 products (category, brand, price, rating)
  - `order_items`: order lines with quantity, discount, net sales and profit
- **Original file:** `ecommerce_sales_customer_analytics_150k.csv`, the combined file the three tables were split from
- The dataset appears to be synthetic (practice) data.

## Tools Used

- MySQL
- MySQL Workbench
- Python (Pandas) to load the CSV files into MySQL

## What I Did

- Designed three tables with primary and foreign keys
- Loaded the data and removed 87 repeated order and product pairs that broke the primary key
- Answered 30 business questions with SQL: counts, totals, averages, filtering, GROUP BY and HAVING
- Used joins to combine products with order items
- Used subqueries to compare products against the average price

## Key Insights

- **Total net sales:** 192,357,753.80, with a **total profit of 82,679,957.72** (about a 43% profit margin).
- **Electronics earns the most profit**, 14,101,155.55, about 17% of all profit.
- **Jewelry and Home Appliances come next**, at 10.39 million and 10.29 million. These top three categories together earn about 42% of total profit.
- **The lowest-profit categories are Books & Media** (1.48 million) and **Grocery** (1.65 million).
- Profit is spread across 15 product categories, so no single category dominates.

## Query Results

| Question | Screenshot |
|---|---|
| Q13: Total revenue | ![Q13](screenshots/Q13_total_revenue.png) |
| Q28: Total profit | ![Q28](screenshots/Q28_total_profit.png) |
| Q21: Profit by category (join) | ![Q21](screenshots/Q21_profit_by_category.png) |
| Q25: Highest-profit category | ![Q25](screenshots/Q25_top_category.png) |
| Q23: Products above average price (subquery) | ![Q23](screenshots/Q23_above_average_price.png) |

## Data Notes

- Totals include all orders, including cancelled, returned and pending ones, because `order_items` has no order status.
- The original data lists several currencies and the amounts were not converted, so totals have no currency symbol.
- For some orders, the item lines add up to more units than the order record in the combined file. All figures here come from `order_items`.
- `order_items` has no order date or customer ID, so sales over time or by customer are not covered.

## Repository Files

| File | Description |
|---|---|
| `ecommerce_sales_analysis.sql` | Database setup and all 30 queries |
| `data/` | Customer and product tables, plus 1,000-row samples of the two large files |
| `screenshots/` | Query results from MySQL Workbench |

## How to Run

1. Open MySQL Workbench and run the table creation section of `ecommerce_sales_analysis.sql`.
2. Load the CSV files from `data/` into the tables. The full order and combined files are too large for GitHub, so the repository has 1,000-row samples of them.
3. Run the queries one at a time to see the results.

## Author

Mayuri Nalage | nalagemayuri111@gmail.com
