# AWS Data Engineering & Analytics Overview - Must Know for AWS MLE Specialty

---

### Real-Time Layer (Kinesis family)  
- **Producers** send data into Kinesis Data Streams  
- Can process streams in real-time with:  
  - Kinesis Data Analytics (SQL or ML on streams)  
  - Lambda (react in real-time)  
  - EC2 apps (custom analytics/ML with SageMaker)  
- Kinesis Data Firehose can buffer & batch data into:  
  - S3 (Parquet/ORC format)  
  - Redshift  
  - OpenSearch (Elasticsearch)  
- Complex combos: streams → analytics → firehose → multiple destinations  

---

### Kinesis Video Layer  
- Video producers (cameras, DeepLens) → Kinesis Video Streams (1 stream per device)  
- ML services (Rekognition, SageMaker) consume video streams → produce data streams  
- Data stream consumers (Lambda, Firehose, Analytics, EC2) react and process in real-time  
- Example: real-time alerts for security footage events  

---

### Batch Layer (Data movement & transformation)  
- Use **Database Migration Service (DMS)** to replicate DB data(from on-prem or RDS)  
- Use **Data Pipeline** to move data from RDS/DynamoDB to S3 in CSV/JSON formats  
- Use **Glue ETL** to transform, clean, enrich data and convert to columnar formats (Parquet)  
- Use **AWS Batch** jobs for auxiliary batch tasks (e.g., S3 clean-up)  

---

### Orchestration & Catalog  
- **Step Functions** orchestrate and monitor workflows spanning multiple services  
- **Glue Data Catalog** indexes data schemas from S3, RDS, DynamoDB, keeping schemas updated with crawlers  

---

### Analytics Layer  
- Analyze data in S3 using:  
  - **EMR** (Hadoop, Spark, Hive)  
  - **Redshift/Redshift Spectrum** (data warehousing + querying S3 directly)  
  - **Athena** (serverless SQL querying on S3)  
- Visualization with **QuickSight** on top of Redshift or Athena  

---

### Exam Recap  
- Understand how real-time, batch, orchestration, catalog, and analytics layers fit together  
- Real-time uses Kinesis Streams, Firehose, Analytics, Lambda, SageMaker  
- Batch layer moves and transforms data via DMS, Data Pipeline, Glue ETL, Batch  
- Step Functions orchestrate workflows across these services  
- Glue Data Catalog centralizes metadata and schema info  
- Analytics is done using EMR, Redshift, Athena, and visualized via QuickSight
