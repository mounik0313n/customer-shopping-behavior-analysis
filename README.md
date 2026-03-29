# Customer Shopping Behavior Analysis 🛒

## 📌 Project Overview
This project performs an end-to-end data analysis on e-commerce customer shopping trends. The goal is to extract actionable business intelligence regarding customer purchasing habits, demographic spending patterns, and the effectiveness of subscriptions and discounts. 

The analysis is broken down into three main phases:
1.  **Data Preprocessing & Exploratory Data Analysis (EDA)** using Python (Pandas).
2.  **In-depth Data Querying & Segmentation** using SQL (PostgreSQL).
3.  **Data Visualization & KPI Reporting** using Microsoft Power BI.

---

## 🛠️ Technical Stack
*   **Python:** `pandas` for data manipulation, cleaning, and statistical imputation.
*   **SQL:** PostgreSQL dialect for complex data aggregations, Common Table Expressions (CTEs), and Window Functions.
*   **Power BI:** For building interactive dashboards and visualizing business metrics.
*   **Jupyter Notebook:** For interactive Python development and documentation.

---

## 📂 Project Structure
```text
📦 customer-trends-data-analysis-SQL-Python-PowerBI
 ┣ 📜 customer_shopping_behavior.csv         # Raw dataset containing ~4000 transactional records
 ┣ 📜 Customer_Shopping_Behavior_Analysis.ipynb # Python EDA and Data Cleaning script
 ┣ 📜 customer_behavior_sql_queries.sql      # Advanced SQL queries for data extraction & segmentation
 ┣ 📜 customer_behavior_dashboard.pbix       # Interactive Power BI Dashboard
 ┗ 📜 Customer-Shopping-Behavior-Analysis.pptx # Final Presentation of insights
```

---

## ⚙️ Technical Implementation Details

### 1. Data Cleaning & Feature Engineering (Python)
The initial phase involved preparing the raw CSV data using `pandas`:
*   **Standardization:** Converted all column headers to `snake_case` for programmatic consistency.
*   **Missing Value Imputation:** Handled null values in the `Review Rating` column by applying a statistical median imputation, grouped by product `Category`, ensuring data integrity without skewing distributions.
*   **Feature Engineering (Binning):** Utilized the `pd.qcut` algorithm to mathematically segment the continuous `Age` variable into discrete categorical quantiles (`Young Adult`, `Adult`, `Middle-aged`, `Senior`).

### 2. Advanced Querying & Customer Segmentation (SQL)
A robust set of SQL scripts was developed to answer key business questions:
*   **Aggregations & Subqueries:** Calculated total revenue by gender and identified high-value customers (spent more than the global average while using a discount).
*   **Window Functions:** Utilized `ROW_NUMBER() OVER (PARTITION BY category ORDER BY COUNT(customer_id) DESC)` to accurately rank and extract the top 3 best-selling products within each category.
*   **Common Table Expressions (CTEs) & CASE Statements:** Engineered a dynamic customer segmentation model, categorizing users into `New` (1 purchase), `Returning` (2-10 purchases), and `Loyal` (>10 purchases) cohorts based on historical transaction frequency.
*   **Performance Metrics:** Evaluated the financial impact of subscription models and shipping preferences using aggregated `SUM` and `AVG` functions.

### 3. Data Visualization & Dashboarding (Power BI)
The refined data was ingested into Power BI to create an interactive analytical dashboard:
*   Visualized KPI metrics such as Total Revenue, Average Order Value (AOV), and Total Customers.
*   Created dynamic charts illustrating demographic revenue contributions, product category performance, and the impact of promotional codes.

---

## 🚀 How to Run the Project

1.  **Python Analysis:** 
    *   Ensure you have Python installed along with Jupyter and Pandas (`pip install pandas jupyter`).
    *   Open `Customer_Shopping_Behavior_Analysis.ipynb` in Jupyter Notebook or VS Code and run the cells sequentially to observe the data cleaning process.
2.  **SQL Queries:** 
    *   Import the `customer_shopping_behavior.csv` into your preferred SQL relational database (e.g., PostgreSQL, MySQL).
    *   Execute the queries located in `customer_behavior_sql_queries.sql` to view the aggregated results.
3.  **Power BI Dashboard:** 
    *   Open `customer_behavior_dashboard.pbix` using Microsoft Power BI Desktop to interact with the visual reports.

---

## 📈 Key Business Insights
*   *(Note: Add 2-3 specific findings here based on your final dashboard, e.g., "Subscribers generated 40% more revenue on average compared to non-subscribers.")*
*   *(e.g., "The 'Adult' demographic quantile contributed the highest volume of sales in the Clothing category.")*
