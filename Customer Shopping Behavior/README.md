# 🛒 Customer Shopping Behavior Analysis
**An End-to-End Data Analysis Project: Python ➔ MySQL ➔ Power BI**

## 📖 Project Overview
This project analyzes customer shopping behavior using a multi-tool approach. The goal was to transform raw retail data into actionable insights regarding customer segmentation, purchasing patterns, and revenue contribution.

### 🛠️ Tech Stack
- **Data Cleaning:** Python (Pandas)
- **Database Management:** MySQL (DML/DDL)
- **Data Visualization:** Power BI
- **Modeling:** Power Query & DAX

---

## 🚀 The Data Workflow

### 1. Data Cleaning & Transformation (Python)
The raw dataset was processed using **Pandas** to ensure data integrity and prepare it for relational database storage.
- **Handling Missing Values:** Imputed missing `review_rating` values using the median relative to the product category.
- **Feature Engineering:** - Created an `age_group` column using quantiles (Young Adult, Adult, Middle-aged, Senior).
    - Mapped `frequency_of_purchases` to a numeric `purchase_frequency_days` for better calculation.
- **Data Normalization:** Standardized column names to snake_case and dropped redundant features like `promo_code_used`.
- **Database Loading:** Used `sqlalchemy` and `pymysql` to export the cleaned DataFrame directly into a MySQL database.

### 2. Exploratory Data Analysis (MySQL)
Once stored in MySQL, I performed complex queries to extract business KPIs:
- **Segmentation:** Categorized customers into *New*, *Returning*, and *Loyal* based on purchase history using **CTEs** and **CASE** statements.
- **Rankings:** Identified top-performing products within each category using **Window Functions** (`RANK() OVER`).
- **Revenue Analysis:** Calculated revenue contribution percentages across different age groups and subscription statuses.

### 3. Data Visualization & Modeling (Power BI)
The final stage involved connecting Power BI to the MySQL database to build an interactive **Customer Behavior Dashboard**.
![Customer Behavior Dashboard]([Customer%20Shopping%20Behavior/Visuals/powerbi_dashboard_preview.png](https://github.com/johnariescaballero/Portfolio-Projects/blob/a06bdbfa7fb467e2c53611b688262e1e8a68931b/Customer%20Shopping%20Behavior/Visuals/powerbi_dashboard_preview.png))

#### **Key Features:**
* **DAX Measures:** Developed custom measures for `Average Purchase Amount`, `Total Revenue`, and `Customer Count`.
* **Data Modeling:** Established a star-schema-style relationship between tables for optimized filtering.
* **Interactive Slicers:** Enabled filtering by Gender, Category, and Shipping Type to allow for deep-dive analysis.

---

## 📈 Key Insights
* **Revenue Contribution:** Middle-aged customers represent the highest revenue contribution compared to other age brackets.
* **Subscription Impact:** Analysis revealed how subscription status correlates with purchase frequency and total lifetime value.
* **Shipping Preferences:** Compared spend behavior between Express and Standard shipping users to identify upsell opportunities.

---

## 📂 How to Use
1. **Python:** Run the `cleaning.ipynb` notebook to see the ETL process.
2. **SQL:** Execute the scripts in `analysis.sql` to view the EDA queries.
3. **Power BI:** Open the `.pbix` file to interact with the dashboard.
