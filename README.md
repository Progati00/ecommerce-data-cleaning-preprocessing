# 🧹 E-Commerce Data Cleaning and Preprocessing

## 📌 Internship Task 1: Data Cleaning and Preprocessing

This repository contains the data cleaning and preprocessing steps for a real-world E-Commerce transaction dataset. This is part of a Data Analyst Internship task to demonstrate proficiency in handling raw, messy data.

---

## 🎯 Objective

Clean and prepare a raw dataset that includes:
- Missing values
- Duplicate entries
- Inconsistent formatting (e.g., dates, column names)
- Mixed data types

The goal is to transform the data into a consistent, analysis-ready format.

---

## 📁 Dataset Overview

- **Original Rows**: 541,909
- **Final Cleaned Rows**: 401,604
- **Columns**:
  - InvoiceNo
  - StockCode
  - Description
  - Quantity
  - InvoiceDate
  - UnitPrice
  - CustomerID
  - Country

---

## 🛠 Tools Used

- Python
- Pandas
- Jupyter Notebook

---

## ⚙️ Steps Performed

### 🔍 1. Missing Values
| Column       | Missing Before | Missing After |
|--------------|----------------|---------------|
| Description  | 1,454          | 0             |
| CustomerID   | 135,080        | 0             |

> ✅ Missing values were handled by:
- Dropping rows with critical nulls (e.g., missing CustomerID)
- Using `.isnull()` to inspect and `.dropna()` to clean

---

### 🔄 2. Removed Duplicates
- Dropped duplicate rows using `drop_duplicates()`
- **Original entries**: 541,909  
- **After removing duplicates**: 401,604

---

### 🧼 3. Standardized Column Names
Converted all column names to lowercase and snake_case:
- `InvoiceNo` → `invoiceno`
- `StockCode` → `stockcode`
- And so on...

---

### 🗂 4. Fixed Data Types
| Column       | Before        | After          |
|--------------|---------------|----------------|
| InvoiceDate  | object        | datetime       |
| CustomerID   | float64       | string/object  |
| Quantity     | int64         | int64          |
| UnitPrice    | float64       | float64        |

> Used `pd.to_datetime()`, `.astype()` to fix data types.

---

### 🧾 Final Cleaned Data Sample
```python
<class 'pandas.core.frame.DataFrame'>
Index: 401604 entries, 0 to 541908
Data columns (total 8 columns):
 #   Column       Dtype         
 ---  ------       -----         
 0   invoiceno     object        
 1   stockcode     object        
 2   description   object        
 3   quantity      int64         
 4   invoicedate   datetime64[ns]
 5   unitprice     float64       
 6   customerid    object        
 7   country       object        
```

---

### 📌 Dataset Source

> E-Commerce Transactions Dataset (with Customer Info) — [https://www.kaggle.com/code/nitin194/online-store-rfm-cohort-analysis/input]
