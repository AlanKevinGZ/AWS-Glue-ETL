# AWS Glue ETL Pipeline for Student Performance Data

## Overview

This project demonstrates an ETL pipeline built with **AWS Glue**, **Amazon S3**, and **PySpark** to process student performance data stored in CSV format.

The pipeline ingests raw student data from Amazon S3, catalogs the dataset using AWS Glue Data Catalog, applies transformations through an AWS Glue ETL Job, and stores the processed results back into Amazon S3. After the ETL process, the generated output file was imported into Spark and Pandas for basic exploratory data analysis (EDA).

---

## Architecture

```
Amazon S3 → AWS Glue Data Catalog → AWS Glue ETL Job → Amazon S3 Output → Spark/Pandas EDA
```

---

## Technologies Used

- AWS Glue
- Amazon S3
- PySpark
- AWS Glue Data Catalog
- Pandas
- IAM
- Snappy Compression

---

## Project Workflow

### 1. Data Ingestion

- Created an Amazon S3 bucket to store the raw dataset.
- Uploaded the `StudentsPerformance.csv` dataset into S3.

### 2. Data Catalog and Schema Definition

- Created a Glue database and table schema for the dataset.
- Configured column types and CSV properties.
- Enabled header handling for correct schema detection.

### 3. ETL Transformation with AWS Glue

- Built an AWS Glue Job to process the dataset using Spark.
- Filtered students with failing grades.
- Configured the ETL output to be stored in a new S3 folder named `reprobados`.

### 4. Output Storage

- The transformed dataset was exported as a compressed Snappy file into Amazon S3.
- Verified ETL execution and output generation inside AWS Glue and S3.

### 5. Spark and Pandas Analysis

- Downloaded the generated Snappy output file from S3.
- Imported the file into Spark DataFrames.
- Converted the Spark DataFrame into a Pandas DataFrame for basic EDA.
- Performed simple analysis such as:
  - Group counts
  - Mean score calculations
  - Basic data inspection and validation

---

## Features

- ETL pipeline using AWS Glue and PySpark
- Data cataloging with Glue Data Catalog
- S3 storage integration
- Snappy compressed output
- Spark DataFrame processing
- Conversion from Spark to Pandas
- Basic exploratory data analysis (EDA)
- IAM/S3 permissions troubleshooting

---

## Example Transformation

Filtered students with failing academic scores and stored the processed results into a separate S3 location for downstream analysis.
