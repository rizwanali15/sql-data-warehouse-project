# 📚 Data Catalog — Gold Layer

## 📌 Overview

The **Gold Layer** represents the business-level data layer of the data warehouse. It contains **dimension tables** and **fact tables** that are structured and optimized for analytical, reporting, and business intelligence use cases.

The Gold Layer provides clean, enriched, and business-ready data that can be directly consumed by reporting tools and analytical queries.

### Gold Layer Tables

- `gold.dim_customers` — Customer dimension
- `gold.dim_products` — Product dimension
- `gold.fact_sales` — Sales fact table

---

# 1. 👤 gold.dim_customers

### Purpose

Stores customer information enriched with demographic and geographic attributes. This dimension provides descriptive information that can be used to analyze sales and customer behavior.

### Columns

| Column Name | Data Type | Description |
|---|---|---|
| `customer_key` | INT | Surrogate key that uniquely identifies each customer record in the dimension table. |
| `customer_id` | INT | Unique numerical identifier assigned to the customer in the source system. |
| `customer_number` | NVARCHAR(50) | Alphanumeric identifier used to track and reference the customer. |
| `first_name` | NVARCHAR(50) | The customer's first name. |
| `last_name` | NVARCHAR(50) | The customer's last name or family name. |
| `country` | NVARCHAR(50) | The country where the customer resides. |
| `marital_status` | NVARCHAR(50) | The customer's marital status, such as `Married` or `Single`. |
| `gender` | NVARCHAR(50) | The customer's gender, such as `Male`, `Female`, or `n/a`. |
| `birthdate` | DATE | The customer's date of birth, stored in `YYYY-MM-DD` format. |
| `create_date` | DATE | The date when the customer record was created in the source system. |

---

# 2. 🛍️ gold.dim_products

### Purpose

Provides detailed information about products and their business attributes. This dimension enables product-level analysis across categories, subcategories, product lines, pricing, and maintenance requirements.

### Columns

| Column Name | Data Type | Description |
|---|---|---|
| `product_key` | INT | Surrogate key that uniquely identifies each product record in the dimension table. |
| `product_id` | INT | Unique identifier assigned to the product in the source system. |
| `product_number` | NVARCHAR(50) | Structured alphanumeric code used to identify and reference the product. |
| `product_name` | NVARCHAR(50) | Descriptive name of the product, including attributes such as type, color, and size. |
| `category_id` | NVARCHAR(50) | Unique identifier representing the product's category. |
| `category` | NVARCHAR(50) | High-level classification used to group related products, such as `Bikes` or `Components`. |
| `subcategory` | NVARCHAR(50) | More detailed classification of the product within its category. |
| `maintenance_required` | NVARCHAR(50) | Indicates whether the product requires maintenance, such as `Yes` or `No`. |
| `cost` | INT | Base cost of the product, measured in whole monetary units. |
| `product_line` | NVARCHAR(50) | Product line or series to which the product belongs, such as `Road` or `Mountain`. |
| `start_date` | DATE | The date when the product became available for sale or use. |

---

# 3. 💰 gold.fact_sales

### Purpose

Stores transactional sales data at the **sales order line-item grain**. It contains measurable business metrics and foreign keys that connect sales transactions to the customer and product dimensions.

This fact table is used for analyzing sales performance by customers, products, dates, quantities, and prices.

### Columns

| Column Name | Data Type | Description |
|---|---|---|
| `order_number` | NVARCHAR(50) | Unique alphanumeric identifier for the sales order, such as `SO54496`. |
| `product_key` | INT | Surrogate key linking the sales transaction to the product dimension. |
| `customer_key` | INT | Surrogate key linking the sales transaction to the customer dimension. |
| `order_date` | DATE | The date when the sales order was placed. |
| `shipping_date` | DATE | The date when the order was shipped to the customer. |
| `due_date` | DATE | The date when the payment for the order was due. |
| `sales_amount` | INT | Total monetary value of the sales line item, measured in whole currency units. |
| `quantity` | INT | Number of units of the product ordered for the sales line item. |
| `price` | INT | Price per unit of the product for the sales line item. |

---
