# data-cleaning-etl-notebooks

Colab notebooks for data cleaning and ETL with pandas (September to October 2025): cleaning public datasets, repairing files that fail a normal import, merging multi-file datasets into one master table, and loading a table into Supabase (Postgres).

## Notebooks

| Notebook | What it does | Data |
|---|---|---|
| `01-data-analyst/online_retail_cleaning.ipynb` | Merges two yearly sheets, drops rows without a customer ID, fixes types, fills missing descriptions from the stock code, adds `TotalPrice` and `IsCancelled` (797,815 rows after cleaning). Also runs quality checks on a 1,143-row ad-conversion dataset. | Online Retail II (UCI); ad-conversion CSV from Kaggle |
| `01-data-analyst/f1_five_source_etl.ipynb` | Loads five raw Formula 1 files (CSV, text, JSON), removes `\N` markers, drops unused columns, fixes types, and merges them into one master table. | Formula 1 results data (Ergast-derived) |
| `01-data-analyst/f1_file_repair.ipynb` | Repairs two files that failed a normal import (UTF-16 tab-separated text, JSON) by trying encoding and separator combinations. | Same F1 data |
| `01-data-analyst/marketing_campaign_quality_checks.ipynb` | Checks types, duplicates and nulls on 200,000 rows, standardizes column names, converts text-typed columns, saves a cleaned CSV. | Marketing campaign dataset (Kaggle) |
| `02-data-engineering/employee_etl_to_supabase.ipynb` | Course challenge: Excel to CSV to Supabase. The direct Postgres connection from Colab failed, so the final version posts batches of 200 rows through the Supabase REST API. | Course material (not included) |

## Data

The datasets are not included. Download them from the public sources listed above and place them in `/content/data` (the path the notebooks use in Colab), or change the paths.

## License

MIT
