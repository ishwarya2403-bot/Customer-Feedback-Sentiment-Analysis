# Customer-Feedback-Sentiment-Analysis
Customer Feedback Data Cleaning using Python | Pandas — A Python data cleaning project focused on preprocessing customer feedback data, handling missing and inconsistent values, standardizing data formats, validating records, and preparing a clean dataset for further sentiment analysis.

# 🧹 Customer Feedback Data Cleaning Using Python

## 📌 Project Overview

Customer feedback data is often collected from different sources such as surveys, reviews, emails, and feedback forms. Before performing any analysis, the raw data needs to be cleaned and standardized to ensure accuracy and consistency.

This project focuses specifically on **data cleaning and preprocessing of customer feedback data using Python and Pandas**.

The objective is to identify and resolve common data quality issues such as missing values, duplicate records, inconsistent formats, invalid dates, inconsistent categorical values, and incorrect data types.

The final output is a **clean and analysis-ready dataset** that can be used for future customer sentiment analysis and other data analytics tasks.

---

## 🎯 Business Context

Organizations collect large amounts of customer feedback, but raw feedback data may contain several quality issues.

For example:

* Missing customer information
* Missing dates
* Duplicate records
* Inconsistent category values
* Different formats for the same value
* Invalid or incorrectly formatted dates
* Inconsistent Yes/No values
* Incorrect data types
* Invalid ratings

If these issues are not handled properly, they can affect the accuracy of future analysis.

Therefore, this project focuses on preparing a reliable and structured dataset before performing any further analysis.

---

## 🎯 Project Objective

The main objective of this project is to:

> **Clean, validate, standardize, and prepare customer feedback data using Python and Pandas for further analysis.**

### Specific Objectives

1. Inspect the raw dataset.
2. Understand the structure and data types.
3. Identify missing values.
4. Detect duplicate records.
5. Handle invalid or inconsistent dates.
6. Standardize categorical values.
7. Validate rating values.
8. Correct inconsistent Yes/No values.
9. Check data types.
10. Identify invalid records.
11. Verify the cleaned dataset.
12. Export the final clean dataset.

---

## 🛠️ Tools & Technologies

| Tool                 | Purpose                                |
| -------------------- | -------------------------------------- |
| **Python**           | Data cleaning and preprocessing        |
| **Pandas**           | Data manipulation and cleaning         |
| **NumPy**            | Numerical and missing-value operations |
| **Jupyter Notebook** | Writing and executing Python code      |

---

## 🔄 Data Cleaning Workflow

```text
Raw Customer Feedback Data
          ↓
Load Dataset
          ↓
Understand Dataset
          ↓
Check Rows & Columns
          ↓
Check Data Types
          ↓
Identify Missing Values
          ↓
Handle Missing Values
          ↓
Check Duplicate Records
          ↓
Clean Date Columns
          ↓
Standardize Categorical Values
          ↓
Validate Ratings
          ↓
Check Invalid Values
          ↓
Final Data Validation
          ↓
Export Clean Dataset
```

---

# 🔍 Data Cleaning Steps

## 1. Load the Dataset

The raw customer feedback dataset was imported into Python using Pandas.

```python
import pandas as pd

df = pd.read_excel("Customer Feedback.xlsx")
```

The dataset was then inspected to understand its structure and contents.

---

## 2. Understand the Dataset

The following functions were used to understand the dataset:

```python
df.head()
df.shape
df.info()
df.describe()
```

These checks helped identify:

* Number of rows
* Number of columns
* Column names
* Data types
* Numerical statistics
* Potential data quality issues

---

## 3. Check Missing Values

Missing values were identified using:

```python
df.isnull().sum()
```

The percentage of missing values was also examined to understand the extent of missing data.

Missing values were then handled according to the nature of each column.

---

## 4. Clean Date Columns

Date columns were checked for inconsistent or invalid date formats.

The date values were converted using Pandas:

```python
df['Date'] = pd.to_datetime(
    df['Date'],
    format='mixed',
    dayfirst=True,
    errors='coerce'
)
```

Using `errors='coerce'` converts invalid date values into `NaT`, allowing them to be identified and handled appropriately.

### Validation

```python
df['Date'].isnull().sum()
```

This helped identify records where the date could not be converted successfully.

---

## 5. Check Duplicate Records

Duplicate records were identified using:

```python
df.duplicated().sum()
```

Duplicate records were reviewed and removed where appropriate.

```python
df = df.drop_duplicates()
```

---

## 6. Standardize Categorical Values

Categorical columns were checked for inconsistent representations of the same value.

For example:

```text
Yes
yes
Y
YES
```

These values represent the same response but may be treated as different categories during analysis.

They were standardized into a consistent format.

Example:

```python
df['Resolved'] = df['Resolved'].replace({
    'Y': 'Yes',
    'N': 'No'
})
```

---

## 7. Validate Rating Values

Customer ratings were checked to ensure that they contained only valid rating values.

The expected rating range was:

```text
1, 2, 3, 4, 5
```

The unique values were checked using:

```python
df['Rating'].unique()
```

This helped identify unexpected or invalid rating values.

---

## 8. Check Data Types

Data types were reviewed using:

```python
df.dtypes
```

Columns were converted to appropriate data types where required.

For example:

* Date → datetime
* Rating → numeric
* Customer ID → appropriate identifier format
* Categorical fields → consistent text format

---

## 9. Validate the Cleaned Dataset

After completing the cleaning process, the dataset was checked again.

```python
df.info()
df.isnull().sum()
df.duplicated().sum()
df.describe()
```

Additional checks were performed to ensure that:

* Missing values were handled appropriately
* Duplicate records were removed
* Dates were standardized
* Ratings were valid
* Categories were consistent
* Data types were appropriate

---

# 📊 Dataset Quality Checks

The project focused on identifying the following data quality issues:

| Data Quality Check   | Purpose                                 |
| -------------------- | --------------------------------------- |
| Missing Values       | Identify incomplete records             |
| Duplicate Records    | Remove repeated observations            |
| Date Validation      | Standardize and identify invalid dates  |
| Rating Validation    | Ensure ratings contain valid values     |
| Category Consistency | Standardize categorical values          |
| Data Types           | Ensure columns have appropriate formats |
| Invalid Values       | Identify unexpected entries             |
| Final Validation     | Confirm dataset is analysis-ready       |

---

# 📁 Project Structure

```text
Customer-Feedback-Data-Cleaning/
│
├── 📂 Data/
│   ├── Customer Feedback.xlsx
│   └── Cleaned_Customer_Feedback.csv
│
├── 📂 Python/
│   └── Customer_Feedback_Data_Cleaning.ipynb
│
├── 📄 README.md
└── 📄 requirements.txt
```

---

# 📌 Project Outcome

The raw customer feedback dataset was transformed into a **clean, standardized, and analysis-ready dataset** using Python and Pandas.

The cleaning process improved the quality of the dataset by:

* Identifying missing values
* Handling invalid dates
* Removing duplicate records
* Standardizing categorical values
* Validating customer ratings
* Correcting data types
* Performing final data quality checks

The cleaned dataset can now be used as a reliable input for future **sentiment analysis, exploratory data analysis, visualization, or machine learning projects**.

---

# 🧠 Key Python Skills Demonstrated

* Python
* Pandas
* Data Inspection
* Data Cleaning
* Missing Value Handling
* Duplicate Detection
* DateTime Conversion
* Data Type Conversion
* Categorical Data Standardization
* Data Validation
* Data Quality Checks
* Dataset Export

---

# 💻 Key Pandas Functions Used

Some of the important Pandas functions used in this project include:

```python
df.head()
df.shape
df.info()
df.describe()
df.isnull().sum()
df.duplicated()
df.drop_duplicates()
df.unique()
df.value_counts()
pd.to_datetime()
df.dtypes
df.dropna()
df.fillna()
```

---

# 🚀 Future Scope

This project currently focuses **only on data cleaning and preprocessing**.

The cleaned dataset can be used as the foundation for future projects such as:

* Customer sentiment analysis
* NLP-based text analysis
* Customer satisfaction analysis
* Exploratory data analysis
* Customer feedback visualization
* Machine learning models

---

## 👩‍💻 Author

**Ishwarya RB**

Aspiring Data Analyst | Python | SQL | Excel | Power BI | Tableau

This project demonstrates my practical knowledge of **Python-based data cleaning and data preprocessing** as part of my Data Analytics portfolio.

