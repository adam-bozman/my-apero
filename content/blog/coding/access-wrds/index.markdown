---
title: "Accessing WRDS with Python"
weight: 3
subtitle: "Taking advantage of Python's flexiblity"
excerpt: ""
date: "2024-05-14"
draft: false
---

# Accessing the WRDS Database

*For a look at my original notebook, take a peek at my [Google Colab](https://colab.research.google.com/drive/1AFz2XYvkeVr53h97fN3p6meWI3VKtChb?usp=sharing)*

---

## A Quick Introduction

The Wharton Research Data Services (WRDS) provides comprehensive data sets for financial, accounting, economic, management, marketing, banking, and insurance research. The WRDS platform offers a user-friendly interface and sophisticated querying capabilities that can be accessed in various ways, one of which is through its Python package. In this notebook, we'll be setting up the environment to connect to the WRDS database using Python.

## Installing WRDS

**What it does:** This line installs the `wrds` package, which provides a Python interface to access the WRDS database.

**Why:** We need to have the `wrds` package installed in our Python environment to establish a connection to WRDS and retrieve data from it.

**Note:** If you are working from a Jupyter notebook, you may need to preface your command with `!` at the beginning, `!pip install wrds -q`. This allows you to run shell commands directly from a Jupyter notebook. The `-q` flag stands for "quiet", which means it will suppress the usual output from the pip command and only show errors, if any.

```python
pip install wrds -q
```

## Import Packages

### `import pandas as pd`

**What it does:** Imports the pandas library and assigns it an alias pd.

**Why:** pandas is a popular data manipulation library in Python. Once you've fetched data from WRDS, it's likely you'll want to work with it in a tabular format, and pandas DataFrames provide a powerful toolset for this purpose.

### `import wrds`

**What it does:** Imports the wrds library.

**Why:** To use the functionalities provided by the wrds package, such as connecting to the WRDS database, you need to import it.

```python
# Load wrds and some common packages (optional)
import pandas as pd
import wrds
```
## Establish a WRDS Connection

**What it does:** Initializes a connection to the WRDS database.

**Why:** Before fetching or querying data from the WRDS, you need to establish a connection to the database. This line ensures that the connection is established and assigns it to the variable conn, which you can use for subsequent operations with the WRDS database. Your prompted username and passwords will be the same as your standard WRDS login. Depending on your settings, a two-factor authentication may be necessary.

```python
# Connect to WRDS
conn = wrds.Connection()
```
## Access a Sample Library (BoardEx)

This code segment is designed to access the board composition data from the WRDS database, specifically from the boardex.na_wrds_org_composition table.

The SQL query selects various details about company directors, such as:

**CompanyID:** The identifier for the company.  
**DirectorID:** The identifier for the director.  
**DirectorName:** The name of the director.  
**Seniority:** The seniority level of the director.  
**CompanyName:** The name of the company.  
**RoleName:** The role of the director in the company.  
**DateStartRole:** The date when the director started the role.  
**DateEndRole:** The date when the director ended the role.  

The query is further filtered to only retrieve records where the DateStartRole is between January 1, 2023, and December 31, 2023.

The result of this query is stored in the Python variable bx. Additionally, the date_cols=['date'] argument suggests an intent to process columns as dates, but there seems to be a discrepancy since there isn't a 'date' column in the selected columns. One might need to adjust this to correctly map to the desired date columns from the SQL query, like date_cols=['DateStartRole', 'DateEndRole'].

```python
# Board Composition Data
bx = conn.raw_sql("""
                    select a.CompanyID, a.DirectorID, a.DirectorName, a.Seniority,
                    a.CompanyName, a.RoleName, a.DateStartRole, a.DateEndRole
                    from boardex.na_wrds_org_composition as a
                    where a.DateStartRole between '01/01/2023' and '12/31/2023'
                    """, date_cols=['date'])
```

## There you go! Happy researching!
