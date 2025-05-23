# Task 7: Get Basic Sales Summary from a Tiny SQLite Database using Python

**Objective:**  
Use SQL inside Python to calculate total quantity sold and total revenue per product, and visualize it with a simple bar chart.

---

## 📁 File Structure
```plaintext
Task7_Sales_Summary/
├── README.md                  # This file
├── sales_data.db              # SQLite database with sample sales data
├── task7_sales_summary.py     # Python script to analyze and visualize data
├── sales_chart.png            # Output chart generated by script (created on run)
```

---

## 📦 Dataset: `sales_data.db`
This SQLite database contains a single table named `sales`:

| Column   | Type    | Description           |
|----------|---------|-----------------------|
| id       | INTEGER | Primary Key (auto)    |
| product  | TEXT    | Product name          |
| quantity | INTEGER | Units sold            |
| price    | REAL    | Price per unit ($USD) |

Sample entries include items like Laptops, Smartphones, Tablets, etc.

---

## 🛠️ How to Run

1. Ensure Python is installed (v3.x)
2. Install required packages:
   ```bash
   pip install pandas matplotlib
   ```
3. Run the script:
   ```bash
   python task7_sales_summary.py
   ```
4. Output:
   - Console: Prints a table showing product-wise total quantity and revenue
   - Image: Saves a bar chart as `sales_chart.png`

---

## 🔍 What the Script Does

- Connects to `sales_data.db` using `sqlite3`
- Runs SQL:
  ```sql
  SELECT product, SUM(quantity) AS total_qty, SUM(quantity * price) AS revenue
  FROM sales
  GROUP BY product;
  ```
- Loads the result into a Pandas DataFrame
- Prints the table to console
- Plots a bar chart of revenue by product using Matplotlib

---

## 🧠 Outcome of This Task
- Learn how to query an SQLite database with Python
- Practice data summarization using SQL
- Visualize revenue using basic Python plots
- Understand integration of `sqlite3`, `pandas`, and `matplotlib`

---
## 🔗 Connect with Me

- [LinkedIn Profile](https://www.linkedin.com/in/aeshaprajapati12/)

