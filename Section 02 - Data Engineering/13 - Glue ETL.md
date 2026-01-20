# AWS Glue ETL - Must Know for AWS MLE Specialty

---

### What is Glue ETL?  
- Fully managed, serverless **Extract, Transform, Load** service  
- Write ETL code in **Python** or **Scala** (Spark or PySpark scripts)  
- No need to manage Spark clusters or resources, pay per usage  

---

### Targets for Glue ETL output  
- Amazon S3  
- JDBC sources/destinations (RDS, Redshift)  
- Glue Data Catalog  

---

### Automation features  
- **Glue Scheduler**: schedule ETL jobs  
- **Glue Triggers**: start jobs on events  

---

### Glue ETL Transformations  
- Common transformations:  
  - DropFields / DropNullFields  
  - Filter records (custom functions)  
  - Join (enrich data)  
  - Map (add/delete fields, external lookups)  
- Supports all Apache Spark transformations, e.g., K-Means algorithm  

---

### Machine Learning in Glue ETL  
- **FindMatches ML Transform**: detects duplicate or matching records even if not exact matches  
  - Useful for data deduplication  

---

### Data formats conversions  
- Convert between CSV, JSON, Avro, Parquet, ORC, XML, etc.  

---

### Exam tips  
- Glue ETL = serverless Spark for data preparation & transformation  
- Supports custom coding and built-in transformations  
- ML-powered FindMatches helps identify duplicates in datasets  
- Integrates with variety of AWS data stores & formats
