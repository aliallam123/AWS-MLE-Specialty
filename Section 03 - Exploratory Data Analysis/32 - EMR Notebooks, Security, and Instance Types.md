# EMR Notebooks, Security, and Instance Types – Key Points for AWS ML Specialty Exam

---

## EMR Notebooks
- Similar to Zeppelin notebooks but **integrated with AWS**.
- Notebook files are **backed up to Amazon S3** (persistent storage).
- Can **provision and manage EMR clusters directly from the notebook**.
- Hosted inside a **VPC** for security.
- Accessed only through the **AWS Management Console** (no direct public URL).
- Supports **Python, PySpark, Spark SQL, SparkR, Scala**.
- Comes with **pre-packaged graphical libraries (Anaconda)** for exploratory analysis and visualization on Spark DataFrames.
- Enables **collaborative multi-user access** on shared EMR clusters.
- **No additional cost** beyond EMR usage.

---

## EMR Security
- **IAM** is the primary method for managing permissions to EMR resources and AWS integrations.
- IAM policies can **restrict actions cluster- or user-level**, including controlling access to EMRFS (S3-backed filesystem).
- **Kerberos authentication** supported (EMR 5+), ensures encrypted credential exchange.
- **SSH** access to cluster nodes uses Kerberos or EC2 key pairs for secure login.
- EMR requires:
  - A **service role** for EMR itself.
  - An **EC2 instance profile role** for cluster nodes.
- **Auto-scaling role** needed if auto-scaling is enabled.
- Integration with **AWS Lake Formation** for security configurations during cluster creation.
- Native integration with **Apache Ranger** for data security on Hive metastore in EMR (optional).

---

## EMR Instance Types
- **Master node**:  
  - Needs minimal capacity (e.g., `m4.large`); upgrade only for clusters >50 nodes.
- **Core and Task nodes**:  
  - Selection depends on workload type:  
    - CPU-intensive: General-purpose (`m4.large`) or CPU-optimized instances.  
    - Memory-intensive: High-memory instances.  
    - Network or ML-heavy: Cluster compute or GPU accelerated instances (e.g., `g3`, `g4`, `p2`, `p3`).
- **Spot Instances**:  
  - Recommended for **Task nodes** to save cost.  
  - Can be added/removed dynamically without impacting cluster storage.  
  - Avoid spot instances for **Core or Master nodes** unless in non-critical testing (risking data loss).
  
---

# Exam Focus Summary
- EMR Notebooks provide interactive Spark development integrated with AWS and backed by S3.  
- Use IAM and optionally Kerberos for secure EMR access and resource control.  
- Master nodes require less compute; customize Core/Task node types based on workload (CPU, memory, GPU).  
- Use Spot instances for Task nodes to reduce cost safely.  
- Apache Ranger integration available for advanced Hive data security.

---
