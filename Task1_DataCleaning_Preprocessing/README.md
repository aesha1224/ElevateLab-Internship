
# Task1_DataCleaning_Preprocessing/README.md

*Objective:*  
Clean and prepare a raw sales‐transactions dataset (handle nulls, duplicates, inconsistent formats) so it’s analysis‑ready.

*Dataset:*  
`train.csv` contains 9 rows of order transactions with the following columns:

| Row ID | Order ID        | Order Date | Ship Date  | Ship Mode    | Customer ID | Customer Name       | Segment   | Country       | City           | State      | Region | Product ID        | Category         | Sub‑Category | Product Name                                                           | Sales    |
|--------|-----------------|------------|------------|--------------|-------------|---------------------|-----------|---------------|----------------|------------|--------|--------------------|------------------|--------------|------------------------------------------------------------------------|----------|
| 1      | CA-2017-152156  | 08-11-2017 | 11-11-2017 | Second Class | CG-12520    | Claire Gute         | Consumer  | United States | Henderson      | Kentucky   | South  | FUR-BO-10001798    | Furniture        | Bookcases    | Bush Somerset Collection Bookcase                                       | 261.96   |
| 2      | CA-2017-152156  | 08-11-2017 | 11-11-2017 | Second Class | CG-12520    | Claire Gute         | Consumer  | United States | Henderson      | Kentucky   | South  | FUR-CH-10000454    | Furniture        | Chairs       | Hon Deluxe Fabric Upholstered Stacking Chairs, Rounded Back             | 731.94   |
| 3      | CA-2017-138688  | 12-06-2017 | 16-06-2017 | Second Class | DV-13045    | Darrin Van Huff     | Corporate | United States | Los Angeles    | California | West   | OFF-LA-10000240    | Office Supplies  | Labels       | Self‑Adhesive Address Labels for Typewriters by Universal               | 14.62    |
| 4      | US-2016-108966  | 11-10-2016 | 18-10-2016 | Standard Class | SO-20335  | Sean O'Donnell      | Consumer  | United States | Fort Lauderdale| Florida    | South  | FUR-TA-10000577    | Furniture        | Tables       | Bretford CR4500 Series Slim Rectangular Table                           | 957.58   |
| 5      | US-2016-108966  | 11-10-2016 | 18-10-2016 | Standard Class | SO-20335  | Sean O'Donnell      | Consumer  | United States | Fort Lauderdale| Florida    | South  | OFF-ST-10000760    | Office Supplies  | Storage      | Eldon Fold 'N Roll Cart System                                          | 22.37    

---

## Files & Folders

```
Task1_DataCleaning_Preprocessing/
├── train.csv
├── cleaned_train.csv
├── excel/
│   └── cleaned_train.csv
├── python/
│   └── DataCleaing.ipynb
└── README.md  ← you are here
```

---

## Deliverables

1. **cleaned_train.csv** – final clean dataset  
2. **Summary of changes** (below)    
3. **Jupyter notebook** (`DataCleaning.ipynb`)

---

## 1. Excel Approach – Step by Step

1. **Import**  
   - *Data → From Text/CSV* → select `train.csv` → *Load*.

2. **Flag & handle missing values**  
   - On header row, apply *Home → Sort & Filter → Filter*.  
   - Select “(Blanks)” in each column to identify empties.  
   - Either **Delete** blank rows or **Fill** with placeholder values (e.g. “Unknown” for text, `0` for numeric).

3. **Remove duplicates**  
   - Select entire table → *Data → Remove Duplicates* → ensure all columns checked → *OK*.

4. **Standardize text fields**  
   - For *Ship Mode*, *Region*, *Category*, *Sub‑Category*:  
     - *Home → Find & Select → Replace* → e.g. replace “second class” → “Second Class”, “west” → “West”, etc.

5. **Rename columns**  
   - Double‑click each header and change to snake_case:  
     - Row ID → row_id  
     - Order ID → order_id  
     - Order Date → order_date  
     - Ship Date → ship_date  
     - Ship Mode → ship_mode  
     - Customer ID → customer_id  
     - Customer Name → customer_name  
     - Segment → segment  
     - Country → country  
     - City → city  
     - State → state  
     - Region → region  
     - Product ID → product_id  
     - Category → category  
     - Sub‑Category → sub_category  
     - Product Name → product_name  
     - Sales → sales

6. **Fix data types & formats**  
   - *order_date*, *ship_date*: select column → right‑click → *Format Cells → Date → YYYY‑MM‑DD* (or use *Text to Columns* to split and reassemble).  
   - *sales*: select column → *Home → Number Format → Number (2 decimals)*.

7. **Save cleaned file**  
   - *File → Save As* → *CSV (Comma delimited)* → name `cleaned_train.csv`.

_See `excel/cleaned_train.csv` for screenshots and detailed guidance._

---

## 2. Jupyter Notebook (Pandas) Approach – Step by Step

1. **Open notebook**  
   - Open `python/DataCleaning.ipynb`.

2. **Import & load**  
   ```python
   import pandas as pd
   df = pd.read_csv('../train.csv')
   df.head()
   ```

3. **Identify missing values**  
   ```python
   df.isnull().sum()
   ```

4. **Handle missing data**  
   ```python
   # Drop rows where all are NaN
   df.dropna(how='all', inplace=True)
   # Fill or drop per‐column:
   df['ship_mode'].fillna('Unknown', inplace=True)
   df['sales'].fillna(0, inplace=True)
   ```

5. **Drop duplicates**  
   ```python
   df.drop_duplicates(inplace=True)
   ```

6. **Standardize text**  
   ```python
   df['ship_mode']     = df['ship_mode'].str.title()
   df['region']        = df['region'].str.title()
   df['category']      = df['category'].str.title()
   df['sub_category']  = df['sub_category'].str.title()
   ```

7. **Convert dates & rename columns**  
   ```python
   df['order_date'] = pd.to_datetime(df['Order Date'], format='%d-%m-%Y')
   df['ship_date']  = pd.to_datetime(df['Ship Date'],  format='%d-%m-%Y')
   df.rename(columns={
       'Row ID':'row_id',
       'Order ID':'order_id',
       'Customer ID':'customer_id',
       'Customer Name':'customer_name',
       'Product ID':'product_id',
       'Product Name':'product_name',
       'Sales':'sales'
   }, inplace=True)
   ```

8. **Convert types**  
   ```python
   df['sales'] = df['sales'].astype(float).round(2)
   ```

9. **Export clean data**  
   ```python
   df.to_csv('../cleaned_train.csv', index=False)
   ```

_Run all cells to reproduce `cleaned_sales_data.csv`._

---

## 3. Summary of Changes

- **Removed** any fully empty rows  
- **Filled** or **dropped** nulls per‑column  
- **Eliminated** duplicate records  
- **Standardized** text (title‑cased ship modes, regions, categories)  
- **Renamed** columns to snake_case  
- **Converted** date strings to `YYYY‑MM‑DD` datetime  
- **Cast** sales to float with two decimals  

---
