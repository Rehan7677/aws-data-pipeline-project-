# AWS Data Ingestion End-to-End Pipeline

## 📌 Project Overview

This project demonstrates an end-to-end data engineering pipeline using AWS services to process candidate application data.

## 🧱 Architecture

* Amazon S3 (Data Lake)
* AWS Glue (ETL Processing)
* AWS Glue Crawler (Schema Detection)
* AWS Athena (Query Engine)

## 🔄 Pipeline Flow

1. Raw CSV files uploaded to S3 (landing layer)
2. AWS Glue converts CSV → Parquet (staging layer)
3. Data is cleaned and stored in final layer
4. Glue Crawler creates metadata tables
5. Athena used for querying and visualization

## ⚙️ Technologies Used

* AWS S3
* AWS Glue (PySpark)
* AWS Athena
* Python

## 📊 Sample Query

```sql
SELECT location, COUNT(*) 
FROM candidate_db.final_final_parquet
GROUP BY location;
```

## 🚀 Key Features

* Scalable data pipeline
* Schema handling and cleaning
* Optimized storage using Parquet
* Serverless querying with Athena

## 📷 Screenshots
<img width="1238" height="580" alt="image" src="https://github.com/user-attachments/assets/7504a57b-88da-4d52-8878-101163122efa" />

## 📌 Future Improvements

* Add partitioning
* Implement Delta Lake / Iceberg
* Automate pipeline using triggers
