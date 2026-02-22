# Day-46-CSV-DB-Pandas

###  Overview

On Day 46, I built a **data flow pipeline** where data moves from a **CSV file → Database → Pandas DataFrame**.
This workflow is extremely common in **data engineering and analytics**, where raw files are stored in databases and later analyzed using Python.

---

##  Workflow Breakdown

```text
CSV File → SQL Database → Pandas DataFrame → Analysis
```

---

## 1️ Load CSV into Database

Data is first read from a CSV file and inserted into a SQL database.

```python
import pandas as pd
import sqlite3

df = pd.read_csv("data.csv")

conn = sqlite3.connect("data.db")
df.to_sql("sales", conn, if_exists="replace", index=False)
```

---

## 2️ Read Data from Database using SQL

Query the database to fetch required data.

```python
query = "SELECT * FROM sales"
df_db = pd.read_sql(query, conn)
```

---

## 3️ Analyze Data using Pandas

Once data is inside Pandas, we can clean and analyze it.

```python
df_db.head()
df_db.describe()
```

---

##  Tools & Technologies

* Python
* Pandas
* SQL (SQLite / MySQL concept)
* CSV files

---

##  Key Learnings

* How CSV files integrate with databases
* Using Pandas as a bridge between SQL and analytics
* Writing SQL queries inside Python
* Real-world ETL and data analysis flow

---

##  Real-World Use Cases

* Data ingestion pipelines
* Business intelligence workflows
* Machine learning data preparation
* Backend analytics systems


