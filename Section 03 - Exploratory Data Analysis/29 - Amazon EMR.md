# Amazon EMR – Key Points for AWS Machine Learning Specialty Exam

---

## What is EMR?
- **Elastic MapReduce (EMR)** is a **managed Hadoop framework on EC2**.
- Includes Hadoop core but extends beyond MapReduce with preinstalled frameworks like:
  - **Apache Spark**
  - **HBase**
  - **Presto**
  - **Flink**
  - **Hive**
- EMR is used for distributed **big data processing and ETL**, critical for preparing massive datasets for ML.
- **EMR Notebooks**: Jupyter-like notebooks running on EMR clusters with AWS integrations, useful for data exploration and ML workflows.

---

## EMR Cluster Components
- A cluster = collection of EC2 nodes, each with a **node type/role**:

  1. **Master (Leader) Node**  
     - Manages cluster coordination, task distribution, and health monitoring.  
     - Every cluster has one Master node.  
     - Can run as a **single-node cluster** (Master node only) for small workloads.

  2. **Core Nodes**  
     - Run processing tasks and **store data on HDFS** (Hadoop Distributed File System).  
     - Multi-node clusters require at least one Core node.

  3. **Task Nodes**  
     - Run processing tasks **only**, no data storage on HDFS.  
     - Optional, ideal for **spot instances** to elastically handle bursts in workload.  
     - Can be added/removed dynamically without impacting cluster storage.

---

## Cluster Types
- **Transient Cluster**  
  - Automatically terminates after completing predefined steps (e.g., data input, processing, storing results).  
  - Cost-efficient for batch jobs/workflows with known workflows.

- **Long-Running Cluster**  
  - Used for interactive or ad hoc analyses where the cluster runs until manually terminated.  
  - Suitable for exploration and experimenting.

---

## Using EMR
- When launching, select applications/frameworks needed (Spark, Hive, Presto, etc.).
- Connect to cluster via Master node SSH or submit ordered **steps**/jobs via AWS console.
- Integrations:  
  - EC2 (nodes)  
  - VPC (networking)  
  - S3 (input/output data storage)  
  - CloudWatch (monitoring and alarms)  
  - IAM (access control)  
  - CloudTrail (audit trail)  
  - AWS Data Pipeline (job scheduling)

---

## Storage in EMR
- **HDFS (Hadoop Distributed File System)**  
  - Default storage system in Hadoop.  
  - Distributes data in **128 MB blocks** across cluster nodes with replication for fault tolerance.  
  - **Ephemeral**: data stored on local node storage; lost if cluster is terminated.  
  - Offers high performance by processing data locally ("data locality").

- **EMRFS (EMR File System)**  
  - Allows using **Amazon S3 as a data store in place of HDFS**.  
  - Provides near-HDFS performance while leveraging durable, persistent S3 storage.  
  - Supports **Consistent View** for strong read-after-write consistency using DynamoDB (optional).  
  - Preferred for persistency as S3 data outlives cluster lifetime.

- **Other Storage**  
  - Local file system: ephemeral, used mainly for staging on Master node.  
  - HDFS can be backed by **EBS volumes** for added storage durability.

---

## Scalability and Resilience
- EMR automatically provisions replacement nodes if a Core node fails.
- Core nodes can be resized on a live cluster.
- Task nodes, often on spot instances, can be added or removed at any time without impacting storage.

---

## Why EMR for Machine Learning?
- Preprocessing huge datasets (scaling, normalization, etc.) by distributing workloads across cluster nodes.  
- Supports big data tools commonly used in ML pipelines such as Spark and Hive.  
- Enables cost management through transient clusters and spot usage.

---

# Exam Focus Summary
- EMR = managed, scalable big data processing cluster with Hadoop + other frameworks like Spark.
- Know **Master, Core, and Task node roles** and their storage responsibilities.
- Understand **Transient vs Long-running clusters** and usage scenarios.
- Storage: ephemeral HDFS storage OR persistent S3 via EMRFS with optional Consistent View.
- EMR integrates with S3, EC2, VPC, IAM, CloudWatch, CloudTrail, and AWS Data Pipeline.
- EMR is critical for distributed data processing when preparing data for ML on massive datasets.

---
