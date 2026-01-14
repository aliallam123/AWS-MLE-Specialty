# AWS Batch - Must Know for AWS MLE Specialty

---

### What is AWS Batch?  
- Managed service to run **batch computing jobs** using **Docker containers**  
- Fully serverless: AWS dynamically provisions required EC2 or Spot Instances based on job volume & requirements  
- No need to manage or provision clusters manually  
- Pay only for underlying EC2 instances launched  

---

### Scheduling & Orchestration  
- Can schedule batch jobs with **CloudWatch Events** (timed runs)  
- Can orchestrate batch workflows using **Step Functions**  

---

### Batch vs Glue  
| Feature         | AWS Batch                              | AWS Glue                          |
|-----------------|--------------------------------------|----------------------------------|
| Use Case        | Any batch job (not limited to ETL)   | ETL focused (Spark jobs, Scala/Python) |
| Environment     | Runs Docker containers on EC2 in your account | Serverless Spark environment managed by AWS |
| Control         | You manage code & instances in your account  | AWS manages Spark clusters & resources |
| Example Job     | Cleanup scripts on S3 buckets, generic batch tasks | Data transformation, cleaning, preparing datasets |
| Resource Type   | EC2 or Spot Instances dynamically provisioned | Serverless, no instance management |

---

### Exam tips  
- Use **Batch** for general batch workloads (not just ETL) that can run in Docker  
- Use **Glue** when you need Spark-based ETL with easy management & data catalog  
- Batch offers more flexibility for arbitrary batch jobs you want to run on-demand or scheduled
