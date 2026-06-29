# 🛒 SQL Retail Sales Analysis

![SQL](https://img.shields.io/badge/SQL-PostgreSQL-blue)
![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-336791)
![GitHub](https://img.shields.io/badge/GitHub-Project-black)
![Status](https://img.shields.io/badge/Status-Completed-success)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Project Overview

This project demonstrates SQL skills by analyzing retail sales data using PostgreSQL.

The objective is to solve real-world business problems using SQL queries and generate meaningful business insights from retail sales data.

This project covers:

- Database Design
- Data Analysis
- Business Intelligence
- Aggregate Functions
- Window Functions
- Common Table Expressions (CTEs)
- Date Functions
- Customer Analysis

---

# 📂 Database Schema

### Table Name: `sales`

| Column Name | Data Type |
|-------------|-----------|
| transactions_id | INT |
| sale_date | DATE |
| sale_time | TIME |
| customer_id | INT |
| gender | VARCHAR |
| age | INT |
| category | VARCHAR(50) |
| quantiy | INT |
| price_per_unit | NUMERIC |
| cogs | NUMERIC |
| total_sale | NUMERIC |

> **Note:** The dataset uses the column name **`quantiy`**. If this is a typo, you may rename it to `quantity` throughout the project.

---

# 🛠 Technologies Used

- PostgreSQL
- SQL
- pgAdmin
- Git
- GitHub

---

# 📚 SQL Concepts Covered

- SELECT Statement
- WHERE Clause
- Aggregate Functions
- GROUP BY
- ORDER BY
- COUNT()
- SUM()
- AVG()
- DISTINCT
- CASE Statement
- Window Functions
- RANK()
- Common Table Expressions (CTEs)
- Date Functions
- EXTRACT()
- TO_CHAR()

---

# 📊 Business Questions Solved

### 1. Retrieve all sales made on **2022-11-05**

```sql
SELECT *
FROM sales
WHERE sale_date = '2022-11-05';
```
<img width="1582" height="901" alt="Screenshot 2026-06-29 170419" src="https://github.com/user-attachments/assets/92aac153-065c-4fcc-a5ee-efc5dfe3a360" />

---

### 2. Retrieve Clothing transactions with quantity greater than or equal to 4 in November 2022

```sql
SELECT *
FROM sales
WHERE category = 'Clothing'
AND TO_CHAR(sale_date,'YYYY-MM')='2022-11'
AND quantiy >= 4;
```

---

### 3. Calculate total sales for each category

```sql
SELECT
category,
SUM(total_sale) AS net_sale,
COUNT(*) AS total_orders
FROM sales
GROUP BY category;
```

---

### 4. Find the average age of customers who purchased Beauty products

```sql
SELECT ROUND(AVG(age),2)
FROM sales
WHERE category='Beauty';
```

---

### 5. Find transactions where total sales exceeded 1000

```sql
SELECT *
FROM sales
WHERE total_sale > 1000;
```

---

### 6. Count transactions by Gender and Category

```sql
SELECT
category,
gender,
COUNT(*) AS total_transactions
FROM sales
GROUP BY category,gender;
```

---

### 7. Find the best-selling month in each year

Uses:

- Window Function
- RANK()
- AVG()

---

### 8. Top 5 customers based on total sales

```sql
SELECT
customer_id,
SUM(total_sale) AS total_sales
FROM sales
GROUP BY customer_id
ORDER BY total_sales DESC
LIMIT 5;
```

---

### 9. Count unique customers in each category

```sql
SELECT
category,
COUNT(DISTINCT customer_id)
FROM sales
GROUP BY category;
```

---

### 10. Analyze sales by shift

Created three business shifts:

| Shift | Time |
|--------|------|
| Morning | Before 12 PM |
| Afternoon | 12 PM – 5 PM |
| Evening | After 5 PM |

Implemented using:

- CASE Statement
- CTE
- EXTRACT()

---

# 🖼️ Query Results — Screenshots

### Table Setup in pgAdmin

![Table Schema Setup](screenshots/table_schema_setup.png)

### Q.1 — Sales made on 2022-11-05

![Sales on Date](screenshots/q1_sales_on_date.png)

### Q.5 & Q.6 — Total sales over 1000 / transactions by gender & category

![Total Sale Over 1000](screenshots/q5_q6_total_sale_over_1000.png)

### Q.8 — Top 5 customers by total sales

![Top 5 Customers](screenshots/q8_top5_customers.png)

### Q.10 — Sales by shift (Morning / Afternoon / Evening)

![Sales by Shift](screenshots/q10_sales_by_shift.png)

---

# 📈 Key Insights

- Identified high-value transactions.
- Found the top five customers based on revenue.
- Measured customer distribution across product categories.
- Identified the best-performing month in each year.
- Analyzed customer purchase behavior by time of day.
- Compared category performance using total sales.

---

# 💡 Skills Demonstrated

- SQL Query Writing
- Data Analysis
- PostgreSQL
- Aggregate Functions
- Window Functions
- CTEs
- Date Functions
- Business Reporting
- Customer Segmentation
- Sales Trend Analysis

---

# 📁 Project Structure

```
SQL-Retail-Sales-Analysis/
│
├── README.md
├── Retail_Sales_Analysis.sql
├── sales_dataset.csv
└── screenshots/
    ├── table_schema_setup.png
    ├── q1_sales_on_date.png
    ├── q5_q6_total_sale_over_1000.png
    ├── q8_top5_customers.png
    └── q10_sales_by_shift.png
```

---

# 🚀 Future Improvements

- Create Power BI Dashboard
- Tableau Dashboard
- Customer Segmentation
- Sales Forecasting
- Stored Procedures
- Views
- Index Optimization
- Interactive Reports

---

# 👨‍💻 Author

## Konatham Lokesh

**Data Engineer | AWS Data Engineer | SQL Developer | Python | PostgreSQL | ETL**

I am passionate about building scalable data solutions and solving business problems using SQL, Python, PostgreSQL, AWS, and Data Engineering technologies.

---

## 🔗 Connect with Me

### 💼 LinkedIn

https://www.linkedin.com/in/konatham-lokesh-718661290/

### 💻 GitHub

https://github.com/Lokesh52-source

---

## ⭐ Support

If you found this project helpful, please consider giving this repository a ⭐ on GitHub.

Thank you for visiting my project!

Happy Learning! 🚀
