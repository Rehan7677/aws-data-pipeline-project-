# AWS Data Pipeline Project (CSV → Parquet → Athena)

## Overview

I built this project to understand how real-world data pipelines work on AWS. The goal was to process candidate data stored in CSV format and make it queryable for analysis.

## What I implemented

* Uploaded raw CSV files into S3 (landing layer)
* Used AWS Glue (PySpark) to convert data into Parquet format
* Created a cleaned dataset in a final layer
* Used Glue Crawler to generate schema automatically
* Queried data using Amazon Athena

## Challenges I faced

* Glue initially misread CSV headers, creating incorrect column names
* Fixed this by explicitly defining schema in the ETL job
* Athena queries didn’t run due to missing output location
* Resolved by configuring S3 query results path

## Key Learnings

* Importance of clean schema in data pipelines
* How Parquet improves query performance
* Debugging Glue jobs and Athena setup

## Sample Query

```sql
SELECT location, COUNT(*) 
FROM candidate_db.final_final_parquet
GROUP BY location;
```

##Screenshots
<img width="1116" height="457" alt="image" src="https://github.com/user-attachments/assets/150e3729-1321-4d0e-a607-d181dbfb59b2" />
<img width="1111" height="478" alt="image" src="https://github.com/user-attachments/assets/6afc9c6e-5ad1-4c01-a349-22023ab84c9b" />
<img width="1338" height="341" alt="image" src="https://github.com/user-attachments/assets/dfd1e639-deb1-4d8a-b2c6-1cdee79daf36" />


## Tech Stack

* AWS S3
* AWS Glue (PySpark)
* AWS Athena

## Future Improvements

* Add partitioning for faster queries
* Automate pipeline using triggers
* Use Iceberg/Delta in production environment
