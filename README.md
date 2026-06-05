# Adventure Works Azure Data Engineering Project

![Azure](https://img.shields.io/badge/Azure-Data%20Engineering-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Data Lake](https://img.shields.io/badge/Architecture-Bronze%20Silver%20Gold-2E7D32?style=for-the-badge)
![SQL](https://img.shields.io/badge/SQL-Serverless%20Views-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)

An Azure data engineering project built around the AdventureWorks dataset. The repository contains raw CSV data, reference scripts, and SQL view definitions for transforming source files into analytics-ready gold-layer views.

## Project Story

This project models a practical modern data platform:

1. Ingest AdventureWorks CSV files.
2. Organize data in a lake-style structure.
3. Transform source data into curated silver outputs.
4. Expose gold-layer SQL views for analytics and reporting.

## Repository Map

| Path | Purpose |
| --- | --- |
| `data/` | AdventureWorks source CSV files for calendar, customers, products, sales, returns, territories, and categories. |
| `Reference Script/silver_layer_refer.ipynb` | Notebook reference for silver-layer preparation. |
| `Reference Script/Create Views Gold.sql` | SQL script for creating gold-layer views over Parquet data. |
| `Reference Script/script` | Supporting script artifact. |
| `Reference Script/git.json` | Project configuration/reference file. |

## Data Assets

The project includes AdventureWorks business entities such as:

- Customers
- Products
- Product categories and subcategories
- Sales transactions from 2015, 2016, and 2017
- Returns
- Territories
- Calendar

## Gold Layer Views

The SQL script creates analytics-facing views for:

| View | Source Concept |
| --- | --- |
| `gold.calendar` | Date and calendar attributes |
| `gold.customers` | Customer profile data |
| `gold.products` | Product attributes |
| `gold.returns` | Product returns |
| `gold.sales` | Sales transactions |
| `gold.subcat` | Product subcategories |
| `gold.territories` | Sales territories |

## Architecture

```text
CSV Sources
    |
    v
Azure Data Lake
    |
    v
Silver Layer Parquet
    |
    v
Serverless SQL Gold Views
    |
    v
Power BI / Analytics
```

## How To Use

1. Review the CSV files inside `data/`.
2. Use the notebook in `Reference Script/` as a silver-layer transformation reference.
3. Run `Create Views Gold.sql` in the Azure Synapse or serverless SQL environment after silver Parquet outputs are available.
4. Connect reporting tools to the `gold` views.

## Future Improvements

- Add a full architecture diagram
- Include pipeline screenshots from Azure Data Factory or Synapse
- Parameterize storage account paths
- Add data quality checks for nulls, duplicate keys, and schema drift
