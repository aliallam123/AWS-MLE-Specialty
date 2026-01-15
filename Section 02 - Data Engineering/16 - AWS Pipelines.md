# AWS Data Pipeline - Must Know for AWS MLE Specialty

---

### What is AWS Data Pipeline?  
- Managed **orchestration service** to move data between sources and destinations  
- Helps manage **task dependencies**, retries, and failure notifications  
- ETL *runs* on **EC2 or EMR instances** within your AWS account (Data Pipeline itself does NOT run the ETL code)  

---

### Common Destinations  
- Amazon S3  
- RDS  
- DynamoDB  
- Redshift  
- EMR  

---

### Use Case Example  
- Move data from RDS or DynamoDB into S3 for ML (e.g., SageMaker)  
- Data Pipeline spins up EC2 instances to run the data movement jobs  
- Supports on-premise data sources as well  

---

### Difference Between Data Pipeline and Glue  
| Feature                  | Data Pipeline                         | AWS Glue                          |
|--------------------------|-------------------------------------|----------------------------------|
| Purpose                  | Orchestration & control over ETL jobs | Fully managed serverless ETL with Spark  |
| Resource management      | Runs on EC2/EMR instances in YOUR account | Runs on AWS-managed resources    |
| Control                  | More control over environment & code | Abstracted, less control          |
| Focus                   | Data movement & orchestration         | Data transformation & cataloging |
| Access to data sources   | Easier for on-premises & private sources | Sometimes limited by AWS permissions |

---

### Exam Tips  
- Data Pipeline = ETL orchestration, runs jobs on EC2/EMR under your control  
- Glue = serverless Spark ETL, managed by AWS, focus on transformation and catalog  
- Use Data Pipeline if you need more control or on-prem integration
