# AWS S3 - Must Know for AWS MLE Specialty

- S3 = object/file storage in buckets  
- Buckets need globally unique names  
- Objects = files with a key (full path)  
  - keys look like folders but are not actual folders  
  - e.g. `my_file.txt` or `folder1/folder2/my_file.txt`

- Max object size = 5 TB (if data >5TB split into multiple objects)  
- Can add object tags (key:value) for classification, security, lifecycle  

---

### S3 for Machine Learning
- backbone storage for many AWS ML services (SageMaker, Athena, Glue...)  
- infinite scaling, no provisioning needed  
- 99.999999999% durability (super reliable)  
- separation of storage (S3) and compute (EC2, Athena, Redshift, Glue...)  
- centralized data lake approach  
- supports any file format (CSV, JSON, Parquet, ORC, Avro, Protobuf...)  

---

### Data Partitioning in S3  
- pattern to speed up queries (especially with Athena)  
- partition by keys like date (year/month/day/hour) or product ID  
- partitions = folders in bucket to filter data efficiently  
- example path: `bucket/mydataset/year=2022/month=10/day=21/data.csv`  
- partition strategy depends on query patterns  
- some AWS tools (e.g. Kinesis) auto partition data for you  

---

### Quick S3 Bucket setup example  
- create bucket with unique name in chosen region  
- create folders to partition data, e.g. `/instructors/2022/10/21/`  
- upload dataset (CSV with instructor data in example)  
- check uploaded file inside partition folders  

---

**Key points to remember:**  
- max object size 5TB  
- keys are "paths" but not real folders  
- partition data based on query needs to improve Athena performance  
- S3 storage is fully decoupled from compute services  
- supports all common data formats for ML workloads   
- infinite, durable, and centralized data lake solution
