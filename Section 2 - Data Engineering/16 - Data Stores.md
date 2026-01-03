# AWS Data Stores Overview - Must Know for AWS MLE Specialty

---

| Service          | Type                  | Use Case / Notes                                                                                |
|------------------|-----------------------|------------------------------------------------------------------------------------------------|
| **Redshift**     | Provisioned Data Warehouse (OLAP) | Columnar-based, massive parallel SQL analytics; query data after loading or via Redshift Spectrum directly on S3 |
| **RDS / Aurora** | Provisioned Relational DB (OLTP) | Row-based, for transactional workloads; stores model metadata or small datasets, not for direct ML training |
| **DynamoDB**     | Serverless NoSQL DB    | Key-value/NoSQL store; good for storing ML model outputs or serving models; no ML processing inside DB |
| **S3**           | Serverless Object Storage | Infinite scaling, object-based storage; main data lake for ML; integrates with almost all AWS services |
| **OpenSearch**   | Search & Analytics     | Indexing and searching large datasets (formerly Elasticsearch); good for clickstream analytics; no built-in ML |
| **ElastiCache**  | In-memory Cache        | Caching hot data for fast access; not used for ML but may appear in questions related to performance |

---

### Key points  
- Redshift = OLAP analytics, big SQL queries, needs provisioning  
- RDS/Aurora = OLTP, transactional relational DB, also needs provisioning  
- DynamoDB = NoSQL, serverless, good for model serving data  
- S3 = main scalable data lake for ML data  
- OpenSearch = indexing & fast search, no ML inside  
- ElastiCache = caching only, not ML-related  

Remember, these are high-level; deep details usually not required for exam.
