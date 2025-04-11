# Nintendo Switch Games ETL Pipeline with Azure Data Factory 🎮👾

## 📌 Project Overview
This project implements an ETL (Extract, Transform, Load) pipeline using Azure Data Factory (ADF) to process Nintendo Switch game data sourced from Kaggle. The pipeline:

1. Extracts raw game data from Azure Blob Storage (CSV).<br>
2. Transforms the data using Mapping Data Flows (cleaning, filtering, aggregating, sorting).<br>
3. Loads the processed data back into Azure Blob Storage (aggregated by year and new dataset with year column).<br>

## 🔹 Key Features
✔ Data Ingestion – Pulls raw Nintendo Switch game data from Kaggle into Azure Blob Storage.<br>
✔ Data Transformation – Cleans and structures data (e.g., extracts release year, filters nulls, aggregates by genre/year).<br>
✔ Automated Workflow – Scheduled ADF pipeline for incremental updates.<br>
✔ Output Storage – Stores processed data in Parquet/CSV for analytics.<br>

## 🛠️ ADF Components Used

| Component           | Purpose                                                                 |
|---------------------|-------------------------------------------------------------------------|
| **Copy Activity**   | Ingests raw data from source into Azure Blob Storage                    |
| **Mapping Data Flow** | Performs data transformations (cleaning, filtering, aggregation)       |
| **Blob Storage**    | Stores both raw and processed data in a structured format                 |
| **Trigger**         | Schedules pipeline execution (e.g., weekly updates)                     |

## 🛠 Azure Data Factory Implementation
1. Ingest Raw Data by copy activity pulls data from Kaggle (or pre-uploaded Blob Storage).
2. Data Flow: Transform & Clean by mapping Data Flow by extracting the year from the date and sorting by User Score.
3. Aggregate by Year: Group data by year and count games per year.
4. Saves New Output to Blob Storage.
