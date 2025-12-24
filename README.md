# ecommerce-analytics-pipeline
Develop an end-to-end e-commerce BI pipeline that extracts and transforms database data, calculates key KPIs, and visualizes metrics in Tableau dashboards to support cross-functional teams and executive decision-making


### E‑Commerce Database Schema
[![Database Schema](https://dbdiagram.io/api/image/embedded/e-commerce-database-design-6947f7a74bbde0fd74ed312c.svg)](https://dbdiagram.io/d/e-commerce-database-design-6947f7a74bbde0fd74ed312c)

<img width="946" height="776" alt="image" src="https://github.com/user-attachments/assets/f9bc403f-aa76-4364-8cca-8c4d3dfb5e4e" />


# E-Commerce BI Project – Analysis & Target KPIs Summary

## Project Objective
Develop an end-to-end BI pipeline to analyze e-commerce sales, marketing campaigns, and customer behavior, and visualize key metrics in dashboards to support decision-making.

---

### 1️⃣ Sales & Revenue KPIs
| KPI | Definition / Formula | Source Table |
| :--- | :--- | :--- |
| **Total Revenue** | Sum of `order_revenue` or `item_revenue` | `fact_orders` / `fact_order_items` |
| **Total Orders** | Count of `order_id` | `fact_orders` |
| **Total Items Sold** | Sum of `quantity` | `fact_order_items` |
| **Average Order Value (AOV)** | Total Revenue ÷ Total Orders | `fact_orders` |
| **Revenue by Product** | Sum of `item_revenue` grouped by `product_id` | `fact_order_items` |
| **Revenue by Customer** | Sum of `order_revenue` grouped by `customer_id` | `fact_orders` |
| **Revenue by Channel** | Sum of `order_revenue` grouped by `channel_id` | `fact_orders` |
| **Revenue by Campaign** | Sum of `order_revenue` grouped by `campaign_id` | `fact_orders` |

### 2️⃣ Customer & Retention KPIs
| KPI | Definition / Formula | Source Table |
| :--- | :--- | :--- |
| **Number of Customers** | Count of distinct `customer_id` | `fact_orders` |
| **New vs Returning Customers** | Compare first order date vs subsequent orders | `fact_orders` |
| **Customer Lifetime Value (CLV)** | Sum of revenue per customer | `fact_orders` |
| **Average Items per Customer** | Total Items Sold ÷ Number of Customers | `fact_order_items` |

### 3️⃣ Product Performance KPIs
| KPI | Definition / Formula | Source Table |
| :--- | :--- | :--- |
| **Top Selling Products** | By quantity sold | `fact_order_items` |
| **Top Revenue Products** | By `item_revenue` | `fact_order_items` |
| **Product Contribution Margin** | (`item_revenue` − `item_cost`) ÷ `item_revenue` | `fact_order_items` |

### 4️⃣ Marketing & Campaign KPIs
| KPI | Definition / Formula | Source Table |
| :--- | :--- | :--- |
| **Campaign Spend** | Sum of spend per `campaign_id` | `fact_campaign_daily` |
| **Campaign Revenue** | Sum of revenue per `campaign_id` | `fact_campaign_daily` |
| **Campaign ROAS** | Revenue ÷ Spend | `fact_campaign_daily` |
| **Campaign CTR** | Clicks ÷ Impressions × 100% | `fact_campaign_daily` |
| **Orders from Campaign** | Count of orders linked to `campaign_id` | `fact_orders` |
| **Revenue by Channel** | Sum of revenue per `channel_id` | `fact_orders` |

### 5️⃣ Operational KPIs
| KPI | Definition / Formula | Source Table |
| :--- | :--- | :--- |
| **Order Fulfillment Rate** | Completed orders ÷ total orders | `fact_orders` (order_status) |
| **Average Items per Order** | Total Items Sold ÷ Total Orders | `fact_order_items` |
| **Profit per Order** | `order_revenue` − `order_cost` | `fact_orders` |
| **Profit per Product** | `item_revenue` − `item_cost` | `fact_order_items` |

### 6️⃣ Optional Advanced KPIs
| KPI | Definition / Formula | Source Table |
| :--- | :--- | :--- |
| **Customer Segmentation** | Revenue or order frequency by `customer_type` | `fact_orders` + `dim_customer` |
| **Product Affinity / Bundles** | Items frequently purchased together | `fact_order_items` |
| **Campaign Effectiveness Over Time** | Trend of ROAS, CTR, and revenue | `fact_campaign_daily` |

---

## Summary
This BI project focuses on sales, marketing, customer, and product performance analysis. All KPIs are designed to support dashboard visualizations for monitoring revenue, campaign efficiency, product performance, and operational metrics.
