# Spark Hospital Readmission and Graph Data Engineering Workflow

A PySpark-based data engineering and machine learning project for analyzing hospital readmission patterns, building a supervised readmission classifier, and importing graph data from Neo4j into Spark for graph-oriented analysis.

This project combines large-scale data preprocessing, Spark MLlib modeling, Spark SQL analytics, and Neo4j graph integration in one reproducible workflow.

---

## Project Overview

Hospital readmission is an important healthcare analytics problem because repeated admissions may indicate patient risk, care gaps, or operational strain. This project uses Apache Spark to clean and analyze hospital readmission records, engineer machine learning features, train a Random Forest classifier, and evaluate readmission behavior across patient groups.

The project also includes a graph data engineering workflow that connects Spark with Neo4j using the Neo4j Spark Connector and imports graph entities as Spark DataFrames for downstream graph-based analysis.

---

## Key Highlights

- Processed **12,465 hospital readmission records** using PySpark.
- Checked for duplicates, missing values, type inconsistencies, placeholder values, and numeric outliers.
- Engineered features from **8 numeric** and **8 categorical** variables.
- Built a Spark ML pipeline using `StringIndexer`, `OneHotEncoder`, `VectorAssembler`, and `RandomForestClassifier`.
- Trained a Random Forest model with **100 trees** and **max depth 8**.
- Evaluated the model on **2,440 unseen test rows**.
- Connected Spark to Neo4j and imported a PlantVitals graph as vertex and edge DataFrames.

---

## Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Big Data | Apache Spark, PySpark |
| Machine Learning | Spark MLlib |
| Graph Database | Neo4j |
| Graph Integration | Neo4j Spark Connector |
| Data Analysis | Spark SQL, DataFrames |
| Environment | Google Colab / Jupyter Notebook |

---

## Dataset

The hospital readmission dataset contains **12,465 records** with patient, admission, medical, and readmission-related features.

The workflow includes:

- Duplicate checks
- Missing value analysis
- Data type validation
- Placeholder value detection
- Numeric outlier review
- Categorical and numeric feature preparation
- Train-test splitting for supervised classification

---

## Workflow

### 1. Data Loading and Inspection

The project begins by loading hospital readmission records into Spark DataFrames and inspecting schema quality, column types, null values, and record counts.

### 2. Data Cleaning

The cleaning workflow checks for:

- Duplicate records
- Missing values
- Invalid or placeholder values
- Type inconsistencies
- Outliers in numeric columns

### 3. Feature Engineering

The model uses **8 numeric** and **8 categorical** variables. Categorical features are encoded using Spark ML transformers, while numeric features are assembled directly into the feature vector.

Main Spark ML components:

```python
StringIndexer
OneHotEncoder
VectorAssembler
RandomForestClassifier
