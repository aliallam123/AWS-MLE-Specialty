# AWS Athena - Must Know for MLE exam

- Athena = serverless SQL query service directly on data in S3  
- No need to load data into DB, queries data "in place"  
- Supports structured, semi-structured & unstructured data (CSV, JSON, Parquet, Avro)  
- Uses Presto under the hood  
- Good for ad hoc querying (e.g. logs, staged data before loading to Redshift)  
- Integrates with:  
  - Jupyter / Zeppelin notebooks (run queries from notebook)  
  - QuickSight (AWS visualization service)  
  - Other BI tools via ODBC/JDBC  
- Works closely with AWS Glue:  
  - Glue crawlers extract schema/metadata from S3 data  
  - Glue Data Catalog used by Athena for schema & SQL column definitions  
  - Glue ETL can transform/convert data (e.g. to columnar formats) to optimize Athena queries  
- Cost: pay per amount of data scanned ($5/terabyte approx)  
  - Use compression and columnar formats (Parquet, ORC) to reduce cost & improve performance  
- Security: uses IAM, S3 bucket policies, ACLs  
  - Supports encryption at rest (SSE-S3, SSE-KMS, CSE-KMS)  
  - TLS encrypts data in transit  
  - Cross-account access possible via S3 bucket policies  
- NOT for:  
  - Highly formatted reports or visualizations (use QuickSight instead)  
  - ETL processes (use Glue ETL instead)  

*Summary*: Athena = serverless, cost-effective way to run SQL queries on S3 data lakes, integrated with Glue catalog & QuickSight for analytics workflows.
