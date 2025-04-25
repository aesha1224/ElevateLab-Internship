# 🛍️ E-Commerce Power BI Dashboard – Interview Project

![E‑Commerce Dashboard](./pic.png)

This project features a professional e-commerce sales dashboard built in Power BI and includes an interview-focused presentation. It demonstrates key metrics, interactive visualizations, and advanced reporting techniques, making it ideal for job interviews and analytics portfolios.

---

## 📁 Project Structure

```plaintext
Dashboard_Design/
├── pic.png                               # Snapshot of the Power BI Dashboard
├── PowerBI_Dashboard_PPT.pptx # PowerPoint presentation with dashboard + interview Q&A
├── README.md                             # Project documentation file

🛠️ Tools & Data
Tool Used: Power BI Desktop

Dataset: Contoso Sales Dataset (includes Region, Country, Net Profit, Sales, Cost of Goods, Return Amount, Discount, Category, Product Brand, Time hierarchy)

🪜 Implementation Steps
Data Import

In Power BI Desktop: Home → Get Data → Excel

Load and review tables like Sales, Product, Geography, Calendar.

Data Cleaning

Use Power Query Editor:

Remove nulls, errors, and duplicates.

Rename columns for clarity.

Create relationships between tables using primary keys.

DAX Measures

DAX
Copy
Edit
Total Sales = SUM('Sales'[SalesAmount])
Total Profit = SUM('Sales'[NetProfit])
Total Quantity = SUM('Sales'[SalesQuantity])
YOY Net Profit % = DIVIDE([Total Profit] - [PY Net Profit], [PY Net Profit])
Additional measures: Cost of Goods, Return Amount, Discount, Order Count, Net Quantity.

Dashboard Design

KPI Cards:

Sales Quantity, Net Quantity, Net Profit, Sales Amount, Cost of Goods, Return Amount, Discount Amount.

Charts:

Net Profit Running Total by Date Hierarchy: Combo chart (column + line) with YOY %.

Quarter-wise Net Profit Running Total: Bar chart.

Year Over Year Net Profit by Product Brand: Waterfall chart.

Geography Table: Table visual with Region, Country, Total Sales, Expenses, Net Profit, Quantity & Orders.

Slicers:

Year, Channel, City, State/Province, Region/Country, Store, Subcategory, Category.

Formatting & Theme

Elegant light theme with teal, gray, and black tones.

Rounded visuals, modern font, and tooltips for clarity.

Consistent alignment and spacing for aesthetics.

Publishing & Summary

Exported dashboard image (pic.png)

Summary PowerPoint (PowerBI_Dashboard_PPT.pptx) includes:

Overview of visuals

Key findings

Business recommendations

💡 Key Insights
Quarter 4 has the highest Net Profit at $1.78bn.

United States leads with the highest sales and profit.

Contoso brand generated $0.11bn Net Profit, contributing significantly to total growth.

YOY Net Profit % fluctuated, showing areas needing improvement.

Net Quantity: Over 13.5M units sold.

Order Count: Surpassed 8.5M globally.

✅ Best Practices Followed
Effective use of KPI Cards for summary stats.

Trend analysis with time-series visuals.

Slicers for regional and product-level filtering.

Clear, intuitive visual hierarchy and color coding.

Responsive layout and professional theme.

