

# Task 4: Dashboard Design – Contoso Report

![Contoso Dashboard](./pic.png)

**Objective**: Design an interactive sales performance dashboard for Contoso that delivers business insights across geographies, product brands, and time periods using Power BI.

---

## 📁 File Structure
```plaintext
Task4_Dashboard_Design/
├── README.md                 # This file
├── pic.png                   # Screenshot of the finished dashboard
├── PowerBI_Dashboard_PPT.pptx        # PPT summary of dashboard insights
```  

---

## 🧰 Tools & Data
- **Tool**: Power BI Desktop  
- **Dataset**: `ContosoSales.csv` (includes Date, Product, Category, Brand, Store, Region, Sales Amount, Cost, Profit, Discount, Quantity)

---

## 🪜 Implementation Steps

1. **Get Data**  
   - Load `ContosoSales.csv` in Power BI via **Home → Get Data → CSV**  
   - Validate columns: Date, Amounts, Profit, Region, Brand, etc.

2. **Data Preparation**  
   - Use **Power Query Editor** to:  
     - Remove nulls/blanks  
     - Ensure proper data types (e.g. Date, Currency)  
     - Rename columns for clarity  
     - Close & Apply

3. **Create DAX Measures**  
   ```DAX
   Sales Quantity = SUM('SalesData'[Sales Quantity])
   Discount Quantity = SUM('SalesData'[Discount Quantity])
   Net Quantity = SUM('SalesData'[Net Quantity])
   Sales Amount = SUM('SalesData'[Sales Amount])
   Discount Amount = SUM('SalesData'[Discount Amount])
   Return Amount = SUM('SalesData'[Return Amount])
   Cost of Goods = SUM('SalesData'[Cost Of Goods])
   Net Profit = SUM('SalesData'[Net Profit])
   ```

4. **Design Layout**  
   - **Header**: Add "Contoso Report" with logo  
   - **KPIs**: Show high-level metrics in cards:  
     - Sales Quantity, Net Profit, Net Quantity, Return Amount, etc.

5. **Visuals Added**  
   - **Net Profit Running Total by Date Hierarchy**:  
     - Combo chart (Column + Line) with YOY %  
   - **Net Profit by Quarter**: Clustered column chart  
   - **Year over Year Net Profit by Product Brand**: Waterfall chart (growth by brand)  
   - **Geography & Store Details**: Table showing breakdown by region/country  

6. **Interactivity & Filters**  
   - Slicers for: Year, Channel, City, State, Region, Store, SubCategory, Category  
   - Dynamic tooltips and labels for clear storytelling

7. **Styling & Theme**  
   - Professional theme with **light background + vibrant accent colors**  
   - Rounded cards, tooltips, shadows, and clear typography  
   - Consistent bar and label formatting

8. **Export & Share**  
   - Export to **PDF or PPT**  
   - Add visuals and summaries in `PowerBI_Dashboard_PPT.pptx`

9. **Summary Presentation Includes**  
   - Dashboard overview and design choices  
   - Explanation of each KPI and chart  
   - Insights by region, brand, and quarter  
   - Recommendations based on performance trends

---

## 🎯 Key Insights from the Dashboard

- **Quarterly Growth**: Net Profit increased from $1.37B (Q1) to $1.78B (Q4)  
- **Brand Performance**: Contoso brand alone contributed $0.11B profit  
- **Top Countries**:  
  - 🇺🇸 United States: Highest profit – $1.01B  
  - 🇬🇧 United Kingdom: $445M  
  - Others: Switzerland, Thailand, Syria contribute significantly  
- **Running Profit Analysis**: YOY profit % fluctuates, with August 2009 showing +4.9% gain  
- **Order Insights**: Over **13.6M units sold**, **8.5M orders**, and **$1.77B net profit**  

---

## ✅ Best Practices Followed

- **Clear KPI Cards** for executive overview  
- **Hierarchical Drilldowns** via Date and Region  
- **Multiple Slicers** for dynamic filtering  
- **Balanced Layout** with performance-focused visuals  
- **Readable Fonts** and tooltips for data storytelling

---

📤 **Deliverables**  
- Dashboard Screenshot: `pic.png`  
- Summary Slides: `PowerBI_Dashboard_PPT.pptx`
