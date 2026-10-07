# Data

Nothing in this folder is committed (see `.gitignore`).

## Source
Federal Judicial Center, **Integrated Database (IDB): Criminal Defendants**
https://www.fjc.gov/research/idb. Public, updated quarterly.

## Expected input

`fjc_cases_cleaned.json`: JSON lines, one row per **charge**, FY2019 + FY2025 (117,443 rows). It was produced by the course team's Databricks ETL from the raw IDB files. The ETL isn't included in this repo.

Columns the notebook uses:

| Column | Meaning |
|---|---|
| `defendant_key` | unique defendant ID (a defendant can have several charge rows) |
| `district` | federal judicial district name |
| `fiscal_year` | 2019 or 2025 |
| `offense_description` | decoded offense description |
| `title_text` | U.S. Code title of the charge (e.g. "ALIENS AND NATIONALITY") |

The audit section also reads `prison_min_months`, `prison_max_months`, `sentence_bucket` and `case_duration_days`. These columns are inspected but not used as features.

Set the path with `export FJC_DATA_PATH=/path/to/fjc_cases_cleaned.json`.
