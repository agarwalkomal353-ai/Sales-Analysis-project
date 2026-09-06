# Sales-Analysis-project
Sales data analysis using Python libraries (Pandas , Matplotlib, Seaborn) and SQL.
# 📊 Sales Performance Analysis

## 📌 Project Overview

This project focuses on analyzing sales performance to uncover meaningful business insights related to sales, profit, products, customers, geography, time trends, and sales targets.

The project uses three related datasets:

* **List of Orders** – Contains order, customer, date, state, and city information.
* **Order Details** – Contains sales amount, profit, quantity, category, and sub-category information.
* **Sales Target** – Contains monthly sales targets by category.

The datasets were cleaned, transformed, merged, and analyzed using **Python and SQL** to understand sales performance and identify areas for business improvement.

---

## 🎯 Project Objective

The main objective of this project is to transform raw sales data into meaningful business insights by:

* Analyzing overall sales and profit performance
* Understanding category and sub-category performance
* Identifying high-performing states and cities
* Analyzing monthly sales and profit trends
* Comparing actual sales with assigned sales targets
* Identifying loss-making and highly profitable orders
* Understanding the relationship between sales, quantity, and profit
* Supporting data-driven business decision-making

---

## 🗂️ Dataset Description

### 1. List of Orders

Contains customer and order-level information.

| Column          | Description             |
| --------------- | ----------------------- |
| `order_id`      | Unique order identifier |
| `order_date`    | Date of the order       |
| `customer_name` | Customer name           |
| `state`         | Customer state          |
| `city`          | Customer city           |

### 2. Order Details

Contains product-level sales information.

| Column         | Description                         |
| -------------- | ----------------------------------- |
| `order_id`     | Order identifier                    |
| `total_sales`  | Sales amount                        |
| `profit`       | Profit or loss from the transaction |
| `quantity`     | Units sold                          |
| `category`     | Product category                    |
| `sub_category` | Product sub-category                |

### 3. Sales Target

Contains monthly category-level sales targets.

| Column                | Description      |
| --------------------- | ---------------- |
| `month_of_order_date` | Target month     |
| `category`            | Product category |
| `target`              | Sales target     |

The original notebook contains **560 order rows, 1,500 order-detail rows, and 36 sales-target rows** before cleaning.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **MySQL**
* **SQL**
* **Jupyter Notebook**

---

## 🔄 Project Workflow

```text
Raw Data
   ↓
Data Understanding
   ↓
Data Cleaning & Preprocessing
   ↓
Data Validation
   ↓
Dataset Merging
   ↓
Exploratory Data Analysis
   ↓
SQL Database Analysis
   ↓
Business Insights
   ↓
Recommendations
```

---

## 🧹 Data Cleaning & Preprocessing

The following preprocessing steps were performed:

* Standardized column names
* Handled missing values
* Checked and removed duplicate records
* Converted date columns into datetime format
* Standardized state and city values
* Validated category and sub-category values
* Validated numerical columns
* Preserved negative profit values because they represent business losses

## The Orders dataset initially contained missing values and duplicate records, which were handled before further analysis.

## 🔗 Data Integration

The datasets were merged using appropriate keys:

* **Orders + Order Details** → `order_id`
* **Merged Data + Sales Target** → `month_of_order_date` and `category`

After merging, the final dataset contained **1,500 rows and 12 columns**.

The cleaned final dataset was also saved as:

```text
final_sales_cleaned.csv
```

---

# 📈 Exploratory Data Analysis

The project includes analysis across multiple business dimensions.

### Category Analysis

* Category-wise total sales
* Category-wise total profit
* Category and sub-category quantity analysis

**Key finding:** Electronics generated the highest total sales, while Clothing generated the highest total profit.

### Geographic Analysis

* Top 10 states by total sales
* Top 10 states by total profit
* Top 10 cities by total sales
* Top 10 cities by total profit

**Key findings:**

* Madhya Pradesh recorded the highest total sales.
* Maharashtra generated the highest total profit.
* Indore recorded the highest city-level sales.
* Pune generated the highest city-level profit.

### Time-Based Analysis

* Monthly sales trend
* Monthly profit trend
* Identification of high and low performing months

**Key finding:** August 2018 recorded the highest monthly sales, while October 2018 recorded the highest monthly profit.

### Target Analysis

Actual sales were compared with assigned category-wise sales targets for the period where target data was available.

The project also handles duplicate target values created during the merge to avoid incorrect target aggregation.

### Sub-Category Analysis

* Top 10 sub-categories by total sales
* Top 10 sub-categories by total profit

**Key finding:** Printers and Bookcases were among the strongest-performing sub-categories in both sales and profit.

### Correlation Analysis

A correlation heatmap was used to study relationships between:

* Sales
* Profit
* Quantity

The analysis indicates that quantity has a positive relationship with sales, while sales and profit have a weaker relationship. This shows that higher sales volume does not necessarily guarantee higher profitability.

---

# 🗄️ SQL Analysis

The project also includes MySQL database analysis.

SQL analysis covers:

### 1. Overall Sales Performance

* Total sales
* Total profit
* Total orders
* Total quantity sold

### 2. Category & Sub-Category Quantity Analysis

* Quantity sold by category
* Quantity sold by sub-category

### 3. Loss-Making Orders

* Identification of orders with negative profit
* Ranking of loss-making orders

### 4. Most Profitable Orders

* Identification of high-profit orders
* Ranking based on profit

The SQL analysis demonstrates the use of:

* `SELECT`
* `WHERE`
* `GROUP BY`
* `ORDER BY`
* Aggregate functions
* Joins
* Filtering and sorting
* Business-oriented SQL analysis

---

# 💡 Key Business Insights

Based on the analysis:

* Total sales were **431,502** with total profit of **23,955** from **500 orders**.
* Electronics was the leading category in terms of sales.
* Clothing generated the highest category-level profit.
* Printers and Bookcases were strong-performing sub-categories.
* Madhya Pradesh was the highest sales-generating state.
* Maharashtra was the highest profit-generating state.
* Indore generated the highest city-level sales.
* Pune generated the highest city-level profit.
* Sales and profit varied significantly across months.
* Several months recorded negative profit, highlighting potential pricing or cost-related issues.
* Loss-making orders were identified, with **B-25798** recording the highest loss.
* **B-25973** was identified as the most profitable order.
* Sales volume alone was not sufficient to explain profitability.

---

# 📌 Business Recommendations

Based on the findings, the business can:

* Focus on high-profit products and sub-categories
* Review pricing and cost structures for loss-making orders
* Analyze regional profitability before expanding sales efforts
* Monitor monthly sales and profit trends
* Improve sales target planning
* Investigate products with high sales but comparatively low profit
* Use quantity, sales, and profit together for performance evaluation

  ## 🚀 How to Run the Project

1. Clone this repository.
2. Install the required Python libraries.
3. Open `Sales_analysis_project.ipynb` in Jupyter Notebook.
4. Run the notebook cells sequentially.
5. For SQL analysis, execute the queries in MySQL after configuring the database connection.


---

# 📁 Project Structure

```text
Sales-Analysis-Project/
│
├── Sales_analysis_project.ipynb
├── final_sales_cleaned.csv
├── README.md
└── data/
    ├── List of Orders.csv
    ├── Order Details.csv
    └── Sales target.csv
```

> **Note:** The raw datasets are not required to be included in the repository if they are subject to licensing or sharing restrictions.

---

---

# 📊 Project Highlights

| Area                | Analysis                                     |
| ------------------- | -------------------------------------------- |
| Data Cleaning       | Missing values, duplicates, data types       |
| Sales Analysis      | Overall and category-wise sales              |
| Profit Analysis     | Category, state, city and order-level profit |
| Product Analysis    | Category and sub-category performance        |
| Geographic Analysis | State and city performance                   |
| Time Analysis       | Monthly sales and profit trends              |
| Target Analysis     | Actual sales vs target                       |
| SQL Analysis        | Aggregation, filtering, grouping and ranking |
| Correlation         | Sales, profit and quantity relationships     |
| Business Insights   | Findings and recommendations                 |

---

# 👩‍💻 Author

**Komal Agarwal**

Data Analytics Project
Python • SQL • Data Analysis • Visualization

