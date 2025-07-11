# 🛒 Zepto E-commerce SQL Data Analyst Portfolio Project

This is a comprehensive, real-world **Data Analyst Portfolio Project** built using SQL on an e-commerce inventory dataset scraped from **Zepto** — one of India’s fastest-growing quick-commerce startups. The project walks through real analyst workflows from raw data exploration to deriving actionable business insights.

---

## 📌 Project Overview

This project simulates how data analysts in retail or e-commerce domains work with messy, unstructured data to extract meaningful insights. You will:

- ✅ Set up and normalize a real-world inventory database  
- ✅ Perform **Exploratory Data Analysis (EDA)**  
- ✅ Clean and transform raw data for analysis  
- ✅ Write **business-driven SQL queries** for revenue, pricing, and inventory decisions  

---

## 👤 Ideal For

- 📊 **Aspiring Data Analysts** building a strong portfolio  
- 📚 Learners practicing **SQL hands-on**  
- 💼 Interview prep for roles in **e-commerce, product analytics, or retail**  

---

## 📁 Dataset Overview

The dataset was originally scraped from [Zepto's](https://www.zeptonow.com/) product listings and hosted on **Kaggle**. It resembles a real-world inventory table where each row represents a **Stock Keeping Unit (SKU)**.

Duplicate product names exist due to multiple weights, sizes, or packaging – just like in a real catalog.

### 🧾 Columns:
| Column | Description |
|--------|-------------|
| `sku_id` | Unique product identifier (Primary Key) |
| `name` | Product name as listed |
| `category` | Product category (e.g., Fruits, Snacks, Beverages) |
| `mrp` | Maximum Retail Price (converted from paise to ₹) |
| `discountPercent` | Discount applied on MRP |
| `discountedSellingPrice` | Final selling price after discount |
| `availableQuantity` | Quantity in stock |
| `weightInGms` | Product weight in grams |
| `outOfStock` | Boolean flag for stock availability |
| `quantity` | Units per package |

---

## 🔧 Project Workflow

### 1. 📥 Database & Table Creation

```sql
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
2. 📂 Data Import 

Using pgAdmin, import the dataset (CSV).
If using terminal:

bash

Copy code

\copy zepto(category,name,mrp,discountPercent,availableQuantity, discountedSellingPrice,weightInGms,outOfStock,quantity) FROM 'data/zepto_v2.csv' WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8'); 

Note: Fix encoding errors by saving the CSV as CSV UTF-8.

3. 🔍 Data Exploration 

Total number of records

Null value checks

Unique product categories

In-stock vs out-of-stock distribution

Duplicate product names/SKUs

4. 🧹 Data Cleaning 

Remove rows where mrp = 0 or discountedSellingPrice = 0

Convert pricing columns from paise to rupees for clarity

Normalize data types and formats

5. 📊 Business Insights 

🔝 Top 10 products with highest discount percentage

❌ High-MRP products currently out of stock

💰 Estimated potential revenue per product category

🧾 Expensive items (MRP > ₹500) with low discount

🏆 Top 5 categories with highest average discount

⚖️ Price per gram analysis for value-for-money products

📦 Weight classification into Low, Medium, Bulk

⚖️ Total inventory weight by product category

🚀 Getting Started 

Clone the repository

Load the dataset into pgAdmin or any PostgreSQL client

Run the provided SQL scripts in order:

01_create_table.sql

02_import_data.sql

03_exploration.sql

04_cleaning.sql

05_analysis.sql

📜 License 

MIT — Free to use, fork, modify, and showcase in your own portfolio or interviews.

👨‍💻 About the Author 

Hey, I’m Vattikuti Kavya — a B.Tech final-year student and aspiring Data Analyst with a strong foundation in SQL, SAP ABAP, and web development.
Connect with me on LinkedIn and feel free to reach out!

⭐️ Show Your Support 

If you find this project helpful:

⭐️ Star the repo

🍴 Fork it

👩‍💻 Use it in your own portfolio

yaml

Copy code

--- Let me know if you'd like a separate `.sql` file structure or GitHub repo structure too. 

window.__oai_logHTML?window.__oai_logHTML():window.__oai_SSR_HTML=window.__oai_SSR_HTML||Date.now();requestAnimationFrame((function(){window.__oai_logTTI?window.__oai_logTTI():window.__oai_SSR_TTI=window.__oai_SSR_TTI||Date.now()}))


Tools

ChatGPT can make mistakes. Check important info. See Cookie Preferences.

