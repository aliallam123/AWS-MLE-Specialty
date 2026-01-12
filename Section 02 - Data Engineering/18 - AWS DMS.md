# AWS Database Migration Service (DMS) - Must Know for AWS MLE Specialty

---

### What is DMS?  
- Service to **migrate databases securely and continuously** to AWS  
- Source database stays available during migration  
- Supports **homogeneous** migrations (e.g., Oracle → Oracle) and **heterogeneous** (e.g., SQL Server → Aurora)  
- Uses **Change Data Capture (CDC)** for continuous replication  
- Requires an **EC2 instance** to run migration tasks  

---

### DMS vs Glue  
| Feature             | DMS                      | AWS Glue                   |
|---------------------|--------------------------|----------------------------|
| Purpose             | Continuous DB migration & replication | Batch ETL processing (Spark) |
| Data transformation | None (just move data)     | Supports complex data transformations  |
| Runtime             | Real-time continuous     | Batch jobs (min 5-minute runs)  |
| Resource management | EC2 instances you control | AWS-managed serverless     |
| Common flow         | Migrate DB to cloud, then transform using Glue ETL | Transform data after migration |

---

### Key exam points  
- DMS = focused on **database migration**, no transformations  
- Runs continuously, uses CDC  
- Glue used after migration for ETL and data prep  
- DMS needs EC2 instance, Glue is serverless  
- Services are complementary, not interchangeable
