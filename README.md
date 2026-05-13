# Superstore Sales & Returns Analysis

> **DEPI Final Project** — End-to-end data analysis and interactive Tableau dashboard built on the Sample Superstore dataset.

---

## Project Structure

```
├── project.ipynb                   # Python data preparation & EDA notebook
├── DEPI_Final_Project_2_.twbx      # Tableau packaged workbook (dashboard)
└── README.md
```

---

## Project Overview

This project performs a full analysis of retail sales, profitability, discounts, and return behavior using the **Sample Superstore** dataset. It combines Python-based data wrangling with a rich Tableau dashboard to uncover actionable business insights.

---


## Dataset

**Sample Superstore** — a classic retail dataset provided by Tableau.

| Sheet | Rows | Key Fields |
|-------|------|------------|
| Orders | ~10,000 | Sales, Profit, Discount, Category, Region, Ship Mode |
| Returns | ~296 | Order ID, Returned |
| People | 4 | Region, Regional Manager |

---

## Tools & Technologies

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Tableau](https://img.shields.io/badge/Tableau-Dashboard-E97627?logo=tableau)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter)

---

## Team Members

Made as part of the **DEPI (Digital Egypt Pioneers Initiative)** final project.

| Name | LinkedIn |
|------|----------|
| Basel Atawya | [linkedin.com/in/basel-atawya](https://www.linkedin.com/in/basel-atawya/) |
| Ahmed Elkholy | [linkedin.com/in/ahmed-elkholy-1ba6602b8](https://www.linkedin.com/in/ahmed-elkholy-1ba6602b8) |
| Karim Bassyouny | [linkedin.com/in/karim-bassyouny-61488b233](https://www.linkedin.com/in/karim-bassyouny-61488b233/) |


---


## Python Notebook — `project.ipynb`

### What it does

| Step | Description |
|------|-------------|
| **Data Loading** | Reads three sheets from `sample_-_superstore.xls`: `Orders`, `Returns`, and `People` |
| **Data Merging** | LEFT JOINs `Returns` on `Order ID`, then `People` on `Region` to build a unified `df_final` |
| **Cleaning** | Fills null `Returned` values with `"No"`, creates a binary `Returned Flag` column |
| **Type Fixing** | Parses `Order Date` and `Ship Date` as proper datetime columns |
| **EDA** | Shape, dtypes, null %, duplicates, descriptive stats, and profit by category |

### Key Libraries

- `pandas`
- `xlrd` (for legacy `.xls` files)

### How to Run

```bash
pip install pandas xlrd
jupyter notebook project.ipynb
```

> Make sure `sample_-_superstore.xls` is placed at the path referenced in the notebook, or update the `file_path` variable accordingly.

---

## Tableau Dashboard — `DEPI_Final_Project_2_.twbx`

Open with **Tableau Desktop** or **Tableau Public** (version 2026.1+).

### Dashboard Sheets

The workbook contains **30+ worksheets** organized around the following themes:

#### KPI Cards
- Total Sales, Total Profit, Profit Margin
- Total Orders, Avg. Order Value, Avg. Return Value
- Shipping Time, Total Discount, Loss Value, Loss %
- Number of Products, Returned Orders Count

#### Profitability Analysis
- Monthly Profit Trend
- Profit Waterfall by Category
- Discount vs. Profit scatter
- Loss % by Region
- Loss by Sub-Category
- The "Loss Leader Matrix"

#### Returns Analysis
- Return Rate vs. Discount
- Return by Category
- Return over Time
- Return Impact Heat Map
- The "Reliability" Check

#### Regional & Customer Analysis
- Regional Manager Scorecard
- Customer Loyalty Cohort Heatmap
- Order Frequency Distribution
- Pareto Chart (top products/customers)
- Shipping Time vs. Profit

#### Interactive Tools
- The "Prioritization" Tool

### Data Model

```
Orders  ──(LEFT JOIN on Order ID)──  Returns
  │
  └──(LEFT JOIN on Region)──  People
```

